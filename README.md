<h1 align="center">Volcano</h1></br>

<p align="center">
🌋 Heatmap charts created in an optimized way, fully customizable for Android.
</p>

## Volcano in Jetpack Compose

If you want to use Volcano in your Jetpack Compose project, check out the **[Volcano in Jetpack Compose](https://github.com/taewooyo/Volcano#volcano-in-jetpack-compose-1)** guidelines.

## How to Use

Volcano supports Kotlin projects, so you can reference it by your language.

```kotlin
val totalValue = dummyData.sumOf { it.value }
val volcano = root {
    name { "Volcano" }
    weight { totalValue }
    sections {
        section {
            name { "GDP Total" }
            weight { totalValue }
            elements {
                dummyData.forEach { gdp ->
                    element {
                        name { gdp.name }
                        weight { gdp.value }
                        percentage { (gdp.oldValue / gdp.value) * 100 }
                        color { getColor((gdp.oldValue / gdp.value) * 100).toLong() }
                    }
                }
            }
        }
    }
}
```

### Create Volcano with Kotlin DSL

We can also create an instance of the Volcano with the Kotlin DSL.

## Volcano in Jetpack Compose

Volcano allows you to display heatmap chart in Jetpack Compose easily.

### Volcano Composable

You can display heatmap with `Volcano` composable function and `Builder` like the below:

```kotlin
val totalValue = dummyData.sumOf { it.value }
val volcano = root {
    name { "Volcano" }
    weight { totalValue }
    sections {
        section {
            name { "GDP Total" }
            weight { totalValue }
            elements {
                dummyData.forEach { gdp ->
                    element {
                        name { gdp.name }
                        weight { gdp.value }
                        percentage { (gdp.oldValue / gdp.value) * 100 }
                        color { getColor((gdp.oldValue / gdp.value) * 100).toLong() }
                    }
                }
            }
        }
    }
}

Volcano(
    modifier = Modifier,
    items = VolcanoBuilder.build(volcano),
    onClickSection = {},
    onClickElement = {},
    selectedBorderColor = Color.Black,
    selectedItem = null,
)
```

# License

```xml
Copyright 2023 taewooyo

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```