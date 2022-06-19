# JSON Schema Extended Directives:

The DIT extension for JSON Schema is an effort to make more JSON Schema-based forms even more dynamic. These specifications are tailored for DIT's needs and will be extended even further as the development team sees fit.

## Baseline 

1. Custom directives goes into the field ***__metadata***
2. The field ***__metadata*** sits next to the standard JSON Schema field definitions such as *type* and *enum*
3. All custom directives names start with double underdashes, including the field ***__metadata*** 

## List of Directives

| Directive Name  | Data Type           | Description                                                  | Consumed by                                                  | Complementary Directive |
| --------------- | ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ----------------------- |
| __isUpload      | boolean             | Used to indicate that a field is an upload field             | **API** for pre-signature. Client for loading the upload aread |                         |
| __labels        | Object (Appendix 1) | Used to hold localization data                               | **Client** uses to display                                   |                         |
| __enumFrom      | array               | Used to indicate where enum data comes from                  | **Client** to create an enum for the specified field in real-time while the other fields with the selector of "enumFrom"are being filled out. |                         |
| __validationApi | String              | Used to indicate that the field needs to be validated by an external API. The value of the field is the URL to the API. | **APIs** to make HTTP calls to the external APIs.            |                         |





## Appendices

### Appendix 1 

```json
{
    ckb: { type: "string" },
    ar: { type: "string" },
    en: { type: "string" },
    nkb: { type: "string" },
    required: ["ckb", "ar", "en"]
}
```
