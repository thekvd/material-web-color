# material-web-color
Update to the algorithms and utilities that power the Material Design 3 (M3) color system, including choosing theme colors from images and creating tones of colors.

I had several issues with the Theme Utilities not generating all of the appropriate colors or applying them.  Keep in mind, this is using ```Scheme``` and not ```DynamicScheme``` for the fix.  ```Scheme``` is going away but in my experience the other doesn't generate the same colors.

I'm putting this here for my own reference and cause it might help others.  I won't be maintaining this one but might be updating when I find better ways while working on my current client.  Hopefully, this won't be needed soon.

Admittedly I'm new to Typescript, so please forgive any unnecessary work I'm about to suggest.  Also, if there's a better way, I'm all ears!

If you add a couple blocks of code to two files here, you can get these to deliver in the Scheme object.

Make sure to install https://www.npmjs.com/package/@material/material-color-utilities first, then make the following changes to a couple files:



### scheme.js

First up is adding these to the bottom of the getters for the Scheme class:
```typescript
    get surfaceDim() {
        return this.props.surfaceDim;
    }
    get surfaceBright() {
        return this.props.surfaceBright;
    }
    get surfaceContainerLowest() {
        return this.props.surfaceContainerLowest;
    }
    get surfaceContainerLow() {
        return this.props.surfaceContainerLow;
    }
    get surfaceContainer() {
        return this.props.surfaceContainer;
    }
    get surfaceContainerHigh() {
        return this.props.surfaceContainerHigh;
    }
    get surfaceContainerHighest() {
        return this.props.surfaceContainerHighest;
    }
    get surfaceTint() {
        return this.props.surfaceTint;
    }
    get primaryFixed() {
        return this.props.primaryFixed;
    }
    get primaryFixedDim() {
        return this.props.primaryFixedDim;
    }
    get onPrimaryFixed() {
        return this.props.onPrimaryFixed;
    }
    get onPrimaryFixedVariant() {
        return this.props.onPrimaryFixedVariant;
    }
    get secondaryFixed() {
        return this.props.secondaryFixed;
    }
    get secondaryFixedDim() {
        return this.props.secondaryFixedDim;
    }
    get onSecondaryFixed() {
        return this.props.onSecondaryFixed;
    }
    get onSecondaryFixedVariant() {
        return this.props.onSecondaryFixedVariant;
    }
    get tertiaryFixed() {
        return this.props.tertiaryFixed;
    }
    get tertiaryFixedDim() {
        return this.props.tertiaryFixedDim;
    }
    get onTertiaryFixed() {
        return this.props.onTertiaryFixed;
    }
    get onTertiaryFixedVariant() {
        return this.props.onTertiaryFixedVariant;
    }
``` 

Next, adding this to lightFromCorePalette:
```typescript
            surfaceDim: core.n1.tone(87),
            surfaceBright: core.n1.tone(98),
            surfaceContainerLowest: core.n1.tone(100),
            surfaceContainerLow: core.n1.tone(96),
            surfaceContainer: core.n1.tone(94),
            surfaceContainerHigh: core.n1.tone(92),
            surfaceContainerHighest: core.n1.tone(90),
            surfaceTint: core.a1.tone(40),
            primaryFixed: core.a1.tone(90),
            primaryFixedDim: core.a1.tone(80),
            onPrimaryFixed: core.a1.tone(10),
            onPrimaryFixedVariant: core.a1.tone(30),
            secondaryFixed: core.a2.tone(90),
            secondaryFixedDim: core.a2.tone(80),
            onSecondaryFixed: core.a2.tone(10),
            onSecondaryFixedVariant: core.a2.tone(30),
            tertiaryFixed: core.a3.tone(90),
            tertiaryFixedDim: core.a3.tone(80),
            onTertiaryFixed: core.a3.tone(10),
            onTertiaryFixedVariant: core.a3.tone(30)
``` 

Last up for this file is adding this to the darkFromCorePalette:
```typescript
            surfaceDim: core.n1.tone(6),
            surfaceBright: core.n1.tone(24),
            surfaceContainerLowest: core.n1.tone(4),
            surfaceContainerLow: core.n1.tone(10),
            surfaceContainer: core.n1.tone(12),
            surfaceContainerHigh: core.n1.tone(17),
            surfaceContainerHighest: core.n1.tone(22),
            surfaceTint: core.a1.tone(80),
            primaryFixed: core.a1.tone(90),
            primaryFixedDim: core.a1.tone(80),
            onPrimaryFixed: core.a1.tone(10),
            onPrimaryFixedVariant: core.a1.tone(30),
            secondaryFixed: core.a2.tone(90),
            secondaryFixedDim: core.a2.tone(80),
            onSecondaryFixed: core.a2.tone(10),
            onSecondaryFixedVariant: core.a2.tone(30),
            tertiaryFixed: core.a3.tone(90),
            tertiaryFixedDim: core.a3.tone(80),
            onTertiaryFixed: core.a3.tone(10),
            onTertiaryFixedVariant: core.a3.tone(30)
``` 

### scheme.d.ts

Add this to the Scheme class: 
```typescript
    get surfaceDim(): number;
    get surfaceBright(): number;
    get surfaceContainerLowest(): number;
    get surfaceContainerLow(): number;
    get surfaceContainer(): number;
    get surfaceContainerHigh(): number;
    get surfaceContainerHighest(): number;
    get surfaceTint(): number;
    get primaryFixed(): number;
    get primaryFixedDim(): number;
    get onPrimaryFixed(): number;
    get onPrimaryFixedVariant(): number;
    get secondaryFixed(): number;
    get secondaryFixedDim(): number;
    get onSecondaryFixed(): number;
    get onSecondaryFixedVariant(): number;
    get tertiaryFixed(): number;
    get tertiaryFixedDim(): number;
    get onTertiaryFixed(): number;
    get onTertiaryFixedVariant(): number;
``` 

Lastly, add this to darkFromCorePalette:
```typescript
        surfaceDim: number;
        surfaceBright: number;
        surfaceContainerLowest: number;
        surfaceContainerLow: number;
        surfaceContainer: number;
        surfaceContainerHigh: number;
        surfaceContainerHighest: number;
        surfaceTint: number;
        primaryFixed: number;
        primaryFixedDim: number;
        onPrimaryFixed: number;
        onPrimaryFixedVariant: number;
        secondaryFixed: number;
        secondaryFixedDim: number;
        onSecondaryFixed: number;
        onSecondaryFixedVariant: number;
        tertiaryFixed: number;
        tertiaryFixedDim: number;
        onTertiaryFixed: number;
        onTertiaryFixedVariant: number;
``` 

Now the Theme Utilities will pull a Scheme object that includes all of the Material Palette (at least the ones listed on m3.material.io).

### Bonus Round

While futzing with this, I noticed the values for lightFromCorePalette's background and surface and darkFromCorePalette's background, surface, and onErrorContainer are off in scheme.js, so I corrected them for my build, but wanted to leave them here in case it's helpful.  Again, using m3.material.io for reference.  If the differences are intentional please let me know.

_NOTE: These blocks also have been reordered with the new additions to group things the way it was originally._

```typescript

// Light
            primary: core.a1.tone(40),
            onPrimary: core.a1.tone(100),
            primaryContainer: core.a1.tone(90),
            onPrimaryContainer: core.a1.tone(10),
            primaryFixed: core.a1.tone(90),
            primaryFixedDim: core.a1.tone(80),
            onPrimaryFixed: core.a1.tone(10),
            onPrimaryFixedVariant: core.a1.tone(30),
            secondary: core.a2.tone(40),
            onSecondary: core.a2.tone(100),
            secondaryContainer: core.a2.tone(90),
            onSecondaryContainer: core.a2.tone(10),
            secondaryFixed: core.a2.tone(90),
            secondaryFixedDim: core.a2.tone(80),
            onSecondaryFixed: core.a2.tone(10),
            onSecondaryFixedVariant: core.a2.tone(30),
            tertiary: core.a3.tone(40),
            onTertiary: core.a3.tone(100),
            tertiaryContainer: core.a3.tone(90),
            onTertiaryContainer: core.a3.tone(10),
            tertiaryFixed: core.a3.tone(90),
            tertiaryFixedDim: core.a3.tone(80),
            onTertiaryFixed: core.a3.tone(10),
            onTertiaryFixedVariant: core.a3.tone(30),
            error: core.error.tone(40),
            onError: core.error.tone(100),
            errorContainer: core.error.tone(90),
            onErrorContainer: core.error.tone(10),
            background: core.n1.tone(98),
            onBackground: core.n1.tone(10),
            surface: core.n1.tone(98),
            onSurface: core.n1.tone(10),
            surfaceVariant: core.n2.tone(90),
            onSurfaceVariant: core.n2.tone(30),
            surfaceDim: core.n1.tone(87),
            surfaceBright: core.n1.tone(98),
            surfaceContainerLowest: core.n1.tone(100),
            surfaceContainerLow: core.n1.tone(96),
            surfaceContainer: core.n1.tone(94),
            surfaceContainerHigh: core.n1.tone(92),
            surfaceContainerHighest: core.n1.tone(90),
            surfaceTint: core.a1.tone(40),
            outline: core.n2.tone(50),
            outlineVariant: core.n2.tone(80),
            shadow: core.n1.tone(0),
            scrim: core.n1.tone(0),
            inverseSurface: core.n1.tone(20),
            inverseOnSurface: core.n1.tone(95),
            inversePrimary: core.a1.tone(80),

// Dark
            primary: core.a1.tone(80),
            onPrimary: core.a1.tone(20),
            primaryContainer: core.a1.tone(30),
            onPrimaryContainer: core.a1.tone(90),
            primaryFixed: core.a1.tone(90),
            primaryFixedDim: core.a1.tone(80),
            onPrimaryFixed: core.a1.tone(10),
            onPrimaryFixedVariant: core.a1.tone(30),
            secondary: core.a2.tone(80),
            onSecondary: core.a2.tone(20),
            secondaryContainer: core.a2.tone(30),
            onSecondaryContainer: core.a2.tone(90),
            secondaryFixed: core.a2.tone(90),
            secondaryFixedDim: core.a2.tone(80),
            onSecondaryFixed: core.a2.tone(10),
            onSecondaryFixedVariant: core.a2.tone(30),
            tertiary: core.a3.tone(80),
            onTertiary: core.a3.tone(20),
            tertiaryContainer: core.a3.tone(30),
            onTertiaryContainer: core.a3.tone(90),
            tertiaryFixed: core.a3.tone(90),
            tertiaryFixedDim: core.a3.tone(80),
            onTertiaryFixed: core.a3.tone(10),
            onTertiaryFixedVariant: core.a3.tone(30),
            error: core.error.tone(80),
            onError: core.error.tone(20),
            errorContainer: core.error.tone(30),
            onErrorContainer: core.error.tone(90),
            background: core.n1.tone(6),
            onBackground: core.n1.tone(90),
            surface: core.n1.tone(6),
            onSurface: core.n1.tone(90),
            surfaceVariant: core.n2.tone(30),
            onSurfaceVariant: core.n2.tone(80),
            surfaceDim: core.n1.tone(6),
            surfaceBright: core.n1.tone(24),
            surfaceContainerLowest: core.n1.tone(4),
            surfaceContainerLow: core.n1.tone(10),
            surfaceContainer: core.n1.tone(12),
            surfaceContainerHigh: core.n1.tone(17),
            surfaceContainerHighest: core.n1.tone(22),
            surfaceTint: core.a1.tone(80),
            outline: core.n2.tone(60),
            outlineVariant: core.n2.tone(30),
            shadow: core.n1.tone(0),
            scrim: core.n1.tone(0),
            inverseSurface: core.n1.tone(90),
            inverseOnSurface: core.n1.tone(20),
            inversePrimary: core.a1.tone(40),
``` 
