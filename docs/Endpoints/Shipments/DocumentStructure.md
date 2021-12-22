# Document structure

## `shipment` object attributes

| Name               | Description                        | Type             | Format          | Restrictions  | Default |
|--------------------|------------------------------------|------------------|-----------------|---------------|---------|
| `shipFrom`         | Sender address                     | `address` object |                 | required (*)  |         |
| `shipTo`           | Receiver address                   | `address` object |                 | required      |         |
| `packages`         | One or more `package` objects      | `package` object |                 | required      |         |
| `goodsDescription` | Description of items being shipped | string           |                 | required      |         |

(*) except when the API client belongs to an already registered resort, in which case it can be omitted (will be ingored);

## `address` object structure

| Name         | Description          | Type   | Format                                            | Restrictions | Maximum length |
|--------------|----------------------|--------|---------------------------------------------------|--------------|----------------|
| `name`       | Name                 | string | Basic Latin string with no special characters (¹) | required (⁵) | 35             |
| `address1`   | Address              | string | Basic Latin string with no special characters (¹) | required (⁵) | 30             |
| `address2`   | Address              | string | Basic Latin string with no special characters (¹) | optional (⁵) | 30             |
| `city`       | City                 | string | Basic Latin string with no special characters (¹) | required (⁵) | 30             |
| `postalCode` | Postal code          | string |                                                   | required (⁵) | 30             |
| `state`      | State / province     | string | 2 letter ISO Alpha-2 code                         | required (⁴) | 20             |
| `country`    | Country              | string | 2 letter ISO Alpha-2 code                         | required (⁵) | 2              |
| `contact`    | Contact name         | string | Basic Latin string with no special characters (¹) | required (⁵) | 35             |
| `phone`      | Contact phone number | number | (²)(³)                                            | optional (⁵) | 25             |
| `email`      | Contact email        | string |                                                   | required (⁵) | 50             |

## `package` object structure

| Name          | Description        | Type                | Format                              | Restrictions |
|---------------|--------------------|---------------------|-------------------------------------|--------------|
| `weight`      | Package weight     | `weight` object     |                                     | required     |
| `dimensions`  | Package dimensions | `dimensions` object |                                     | required     |

## `weight` object structure

| Name    | Description  | Type   | Format                                           | Restrictions |
|---------|--------------|--------|--------------------------------------------------|--------------|
| `value` | Weight value | number | (³)(⁶)                                           | required     |
| `units` | Weight units | number | Currently the only accepted value is 1, for "KG" | required     |

## `dimensions` object structure

| Name     | Description      | Type   | Format                                           | Restrictions |
|----------|------------------|--------|--------------------------------------------------|--------------|
| `length` | Package length   | number | (³)(⁶)                                           | required     |
| `width`  | Package width    | number | (³)(⁶)                                           | required     |
| `height` | Package height   | number | (³)(⁶)                                           | required     |
| `units`  | Dimensions units | number | Currently the only accepted value is 1, for "KG" | required     |

(¹) Data containing special characters will be rejected;

(²) For `US`, `phone` should start with 1 and contain 11 digits;

(³) Numbers containing non-numeric characters will be rejected; Please make sure to use the point (`.`) as decimal separator;

(⁴) `state` is required only for the following countries: IT, CA, US;

(⁵) For the `shipTo` address, only the `country` and `email` fields are required; all others are optional and can be omitted;

(⁶) Any value using a fractional part must use a period as the decimal separator;
