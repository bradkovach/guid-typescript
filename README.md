# Guid Typescript

Guid Typescript is a library that generates valid v4 GUID/UUID strings.

## Changelog

### Version 1.0.9

- Library now generates valid v4 GUID/UUID values. Some GUID/UUID parsers were causing parser errors because version/variant fields were not set properly.
- Tests added to verify v4 GUID/UUID generation and validation

#### Deprecated

- The `toJSON()` method should be replaced with a call to `toObject()`. The `toJSON()` did not produce JSON. This method should be eliminated in version 1.1.0. Any uses of `toJSON()` will produce a console warning.

#### Updating

Changes are non-breaking. Please update immediately.

## Installation and usage

### Installation

```bash
npm i guid-typescript --save
```

### Basic usage

```typescript
import { Guid } from "guid-typescript";

export class Example {
  public id: Guid;
  constructor() {
    this.id = Guid.create(); // ==> b77d409a-10cd-4a47-8e94-b0cd0ab50aa1
  }
}
```

## Props and Methods

| Method/Prop                        | Description                                                                    | Test | Status         |
| ---------------------------------- | ------------------------------------------------------------------------------ | ---- | -------------- |
| static VERSION: string             | The GUID/UUID version used. Always `4`.                                        | OK   | Ready          |
| static VARIANTS: string[]          | An array of valid VARIANT hexadecimal string values, `8`, `9`, `a`, and `b`.   | OK   | Ready          |
| static validator: RegExp           | A non-global Regular Expression that will validate a v4 GUID/UUID.             | OK   | Ready          |
| static isGuid (guid: any): boolean | Check if value is a guid code                                                  | OK   | Ready          |
| static create ( ): Guid            | Create a new guid                                                              | OK   | Ready          |
| static createEmpty ( ): Guid       | Create an empty guid                                                           | OK   | Ready          |
| static parse (guid: string): Guid  | Creates a guid instance from a given guid as string                            | OK   | Ready          |
| static raw ( ): string             | Create a guid code in string format                                            | OK   | Ready          |
| equals (other: Guid): boolean      | Compare a guid code                                                            | OK   | Ready          |
| isEmpty ( ): boolean               | Validate if a guid is empty                                                    | OK   | Ready          |
| toString ( ): string               | Parse a guid instance to string format                                         | OK   | Ready          |
| toObject ( ): any                  | Return the GUID as a JavaScript object                                         | OK   | Ready          |
| toJSON ( ): any                    | Return the GUID as a JavaScript object. _Deprecated_ Use `toObject()` instead. | OK   | **DEPRECATED** |
