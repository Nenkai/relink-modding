---
icon: material/palette-swatch-variant
---

# Material Info - .mmat

`.mmat` represents all the materials for a model, it is a set of materials. It describes the textures to use, and the shaders linked to a material.

This file is a [FlatBuffer](https://flatbuffers.dev/) file. 

* [Flatbuffer Schema](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.fbs)
* [010 Editor Template](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.bt)

## Header

| Field Name            | Type           | Description                                        |
|-----------------------|----------------|----------------------------------------------------|
| magic                 | uint           | Should be `20230727`, **explicitly checked**. Might correspond to a date, 2023/07/27. |
| materials             | [Material](#material)[] | List of all materials in the material set.
| constant_buffers      | [ConstantBuffer](#constantbuffer) | List of constant buffers.
| shader_param_float_data_pool | float[] | Float data for materials when their parameters uses floats/Vectors.
| byte5                  | byte           | Unknown. `em` files seem to use this.
| bool6                  | bool           | Unknown.
| bool7                  | bool           | Unknown.

---

### Material

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| shader_params         | [ShaderParamInfo](#shaderparaminfo)[] | Shader parameters, which shaders to use.                      |
| texture_maps          | [TextureMapInfo](#texturemapinfo)[]   | Textures to use.
| constant_buffer_indices | uint              | Indices of which [constant buffers](#constantbuffer) to use.
| granite_params        | [GraniteVirtualTextureStreamingInfo](#granitevirtualtexturestreaminginfo) | Granite SDK Texture streaming info. If not present, will load textures loose.
| unique_material_name_hash_maybe | XXHash32Custom(str) | Hash of the name of this material.
| shader_type           | byte              | Type of shader to use.
| shader_sub_type       | byte              | Sub-type of shader.
| unk_8                 | byte              | Unknown. Should be 0 to 3.
| bool9                 | bool              | Unknown.
| bool10                | bool              | Unknown.
| bool11                | bool              | Unknown.
| bool12                | bool              | Unknown.

??? abstract "Shader Type"

    Each shader type uses a different type of shader where **different parameters and texture maps may be required to be provided**. Refer to files which uses these types in the first place to provide the proper parameters to avoid a potential game crash.

    * 0 = player_silhouette? (sub-types: 7, 8)
    * 1 = player_silhouette2? (sub-types: 7, 8)
    * 2 = Eye shaders? (sub-types: 7, 8)
    * 3 = Face shaders? (sub-types: 0, 3, 7, 8)
    * 4 = Hair shaders? (sub-types: 0, 3, 7, 8)
    * 5 = Metal shaders (sub-types: 0, 3, 4, 5, 7, 8)
    * 7 = `elementallookdev` (sub-types: 7, 8)
    * 8 = `flowmap` (sub-types: 7, 8)
    * 9 = `foilage` (sub-types: 7, 8)
    * 10 = `glowingground` (sub-types: 7, 8)
    * 11 = `glowingmountain` (sub-types: 7, 8)
    * 12 = `ice` (sub-types: 2, 3, 7, 8)
    * 13 = `ice_2layer` (sub-types: 7, 8)
    * 14 = `lavafall` (sub-types: 7, 8)
    * 15 = `lucilius` (sub-types: 7, 8)
    * 16 = Not supported
    * 17 = `plantbillboard` (sub-types: 7, 8)
    * 18 = `plantmiddleview` (sub-types: 4, 7, 8)
    * 19 = `plantshake` (sub-types: 4, 7, 8)
    * 20 = `skycloud` (sub-types: 1, 7, 8)
    * 21 = `uberenv` (sub-types: 1, 7, 8)
    * 22 = `uberenv_layer2` (sub-types: 1, 7, 8)
    * 23 = `uberenv_layer2_plantpivotpainter` (sub-types: 1, 7, 8)
    * 24 = `uberenv_layer3` (sub-types: 1, 7, 8)
    * 25 = `uberenv_layer4` (sub-types: 1, 7, 8)
    * 26 = `uberenv_plantpivotpainter`? (sub-types: 4, 7, 8)
    * 27 = `uberenvtextureless`? (sub-types: 7, 8)
    * 28 = Not supported
    * 29 = `grid` (sub-types: 7, 8)

??? abstract "Shader Sub-Type"
    The sub-types supported **depend** on the main shader type.

    * 0 = vs_pbs_xxxxx/vs_pbs_sxxxx8_anime/vs_pbs_sxxxx/vs_pbs_sxxxx_anime
    * 1 = ?
    * 3 = outline (skinning)
    * 4 = shadow
    * 5 = shadow skinning mask (dp)
    * 6 = pointlight_shadow_mask
    * 7 = player silhouette or regular texture?
    * 8 = "foward" shaders?

---

#### ShaderParamInfo

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| param_hash            | XXHash32Custom(str) | Hashed shader parameter name.                    |
| value_or_offset       | uint | Value for the parameter. Note that when the type is `float/Vec2/Vec3/Vec4`, the value becomes an offset to `shader_param_float_data_pool`.
| value_type            | ShaderParamValueType  | Parameter value type. 

!!! note "Value Types"

    * `U8` = 0,
    * `U16` = 1,
    * `F32` = 2,
    * `Vec2` = 3
    * `Vec3` = 4,
    * `Vec4` = 5

---

#### TextureMapInfo

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| shader_map_name_hash  | XXHash32Custom(str) | Hashed map name passed to the shader.            |
| texture_name          | string | Texture name. When granite is not in use, this will be mapped to `texture/4k/<name>.texture` or `texture/<name>.texture`.

---

#### GraniteVirtualTextureStreamingInfo

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| page_file             | string            | Granite page file where textures for this material are located.  |
| layer_to_shader_map_name_hash | XXHash32Custom(str)[] | Shader map names. Each element will map to one layer in the granite file. For instance if element 0 is the hash of `g_AlbedoMap`, that means that `g_AlbedoMap` is located at layer 0. |
| unk3                  | byte | Unknown.
| unk4                  | byte | Unknown.
| tile_set_number       | byte | Tile set number where the page file is located. Up to 11 is supported, 0-2 is used.

---

### ConstantBuffer

Unknown. This is indexed by `constant_buffer_indices` within materials.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| buffer                | float[]           | Float buffer.  |
| unk_unique_param_name_hash | XXHash32Custom(str) | Unique name hash. |

## Known Hashes

??? abstract "Shader Maps"

    Strings can be found inside shaders.
    
    ```
    enum ShaderMapTypeHash : uint
    {
        Unk = 0,
        g_5A2C820C             = 0x5A2C820C,
        g_8A0507FB             = 0x8A0507FB,
        g_AlbedoMap            = 0x3F2B4D59,
        g_AlbedoMapFar         = 0x7847F758,
        g_AlbedoMapMiddle      = 0x56C35C30,
        g_AlbedoTex            = 0xE9AEA597,
        g_AlbedoTex0           = 0x7D82DDEA,
        g_AlbedoTex1           = 0x8FC0A070,
        g_AlbedoTex2           = 0x19615C52,
        g_AlbedoTex3           = 0xA697D782,
        g_AreaMaskMap          = 0xD52525E5,
        g_Base0Map             = 0x9EE04147,
        g_Base1Map             = 0x46C247DB,
        g_BottomErosion0Map    = 0xAD237ACF,
        g_BottomErosion1Map    = 0x47DA21A1,
        g_BumpMap              = 0xE19336DE,
        g_BumpMaskMap          = 0x707A6889,
        g_BumpNormalMap        = 0x9B7115C3,
        g_Color0Map            = 0x7AF0C744,
        g_Color1Map            = 0xC5089B10,
        g_ContainerMap         = 0x6C92581E,
        g_DetailNormalMap      = 0x71F4A50E,
        g_DitherMap            = 0x0C914331,
        g_EmissiveMap          = 0x5CDF6E8F,
        g_EyeHighLightTexture  = 0x00B36A70,
        g_EyeIrisTexture       = 0x637A19F3,
        g_EyeWhiteTexture      = 0xAEDB57AE,
        g_FlowMap              = 0x983C09F6,
        g_IBLTexture           = 0x330CF7B7,
        g_Large0Map            = 0xC56364D9,
        g_Large1Map            = 0x9FEF4F43,
        g_Layer1Map            = 0x7373F664,
        g_Layer2Map            = 0x3779219E,
        g_LowDetailMap         = 0xF8E10DF2,
        g_LUT                  = 0x69DF53A1,
        g_Mask0Map             = 0xDB972A87,
        g_Mask1                = 0x847A6CBD,
        g_Mask1Map             = 0x42904E14,
        g_Mask2                = 0x6137BA13,
        g_Mask2Map             = 0x2D04F715,
        g_Mask3                = 0x35091AFA,
        g_Mask4                = 0x393263EF,
        g_MaskMap              = 0x63C1ED71,
        g_MaskMap1             = 0x3DCC2032,
        g_MaskTex              = 0xD19EA412,
        g_MaskTex0             = 0xAE860AB0,
        g_MaskTex1             = 0x3069DB65,
        g_MaskTex2             = 0xEDD2D2AF,
        g_MaskTex3             = 0x4CC0E7B6,
        g_Middle0Map           = 0x38054382,
        g_Middle1Map           = 0xB70FDCD5,
        g_MROEMap              = 0x4905E4E4,
        g_MROMap               = 0x7852D3FE,
        g_Noise0Map            = 0x451D0F3A,
        g_Noise1Map            = 0x62F4BBF8,
        g_NoiseGradationMap    = 0xB21CCD8B,
        g_NoiseMap             = 0x7159CBC3,
        g_NoiseMaskMap         = 0x010A5EFA,
        g_NormalMap            = 0xADBA7C37,
        g_NormalMap1           = 0x1470B2FB,
        g_NormalTex            = 0xE752FF91,
        g_NormalTex0           = 0xB55D7961,
        g_NormalTex1           = 0xFB542B74,
        g_NormalTex2           = 0x295ED71A,
        g_NormalTex3           = 0x82A0AA5A,
        g_OffsetMask0Map       = 0x6ECBBABD,
        g_OffsetMask1Map       = 0xAD768A4F,
        g_ParallaxTexture      = 0x1EE34406,
        g_SideErosion0Map      = 0x1EC206C2,
        g_SideErosion1Map      = 0xE21BFE74,
        g_SideNoiseMap         = 0xA7D31F31,
        g_SparkleNormalMap     = 0x64E256E8,
        g_UberColorNoiseMap    = 0xC19A4B09,
        g_WindMaskMap          = 0x1DD2F116,
    }
    ```

??? abstract "Shader Parameters"

    Strings can be found inside shaders.

    ```
    enum ShaderParameterTypeNameHash : uint
    {
        Unk = 0,
        g_037BE4E5             = 0x037BE4E5,
        g_EmissivePower        = 0x06CFE5A4,
        g_0A05A26F             = 0x0A05A26F,
        g_11664BFC             = 0x11664BFC,
        g_EnableDiscardMask    = 0x24C1ABA9,
        g_2AEDA6AD             = 0x2AEDA6AD,
        g_2B5C866C             = 0x2B5C866C,
        g_372C03F0             = 0x372C03F0,
        g_UseIceEmissive0      = 0x3C966EE3,
        g_4298F7E4             = 0x4298F7E4,
        g_EnableOutLine        = 0x49D8C1B9,
        g_53F49792             = 0x53F49792,
        g_56346692             = 0x56346692,
        g_IsUseAlbedoAlphaClip = 0x60F31A22,
        g_IsUseDetailNormal    = 0x6C5CB9AC,
        g_IsUseDitherMap       = 0x7920C84F,
        g_EnableBooleanMask    = 0x920821E1,
        g_92339519             = 0x92339519,
        g_93D9F63A             = 0x93D9F63A,
        g_SwayAmplitude        = 0x98EBBEC2,
        g_9C83F56F             = 0x9C83F56F,
        g_ContainerUse         = 0x9F1DA064,
        g_A6EB1B34             = 0xA6EB1B34,
        g_AB261CFA             = 0xAB261CFA,
        g_AC6F995D             = 0xAC6F995D,
        g_B0EA41D9             = 0xB0EA41D9,
        g_B460A0F0             = 0xB460A0F0,
        g_BAEF6920             = 0xBAEF6920,
        g_C5BD3DED             = 0xC5BD3DED,
        g_C9762248             = 0xC9762248,
        g_UseIceEmissive       = 0xCA06A6B6,
        g_TwoSided             = 0xD94F2821,
        g_UseColorNoise        = 0xE208C4C4,
        g_E56343C0             = 0xE56343C0,
        g_EB6F1AE7             = 0xEB6F1AE7,
    }
    ```