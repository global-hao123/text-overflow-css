## text-overflow universal solution

There is a pure CSS universal solution of "text-overflow: ellipsis"

## Compatibility

Chrome 1+ / Firefox 10+ / Opera 9+ / IE 8+

## Feature

- single/multi line supports
- rtl/ltr supports
- Responsive supports
- custom ellipsis supports
- i18n supports

### Why not use block + "overflow:hidden"?

- The end of the text may appear half the characters
- No way to add custom-ellipsis

### Why not handle in Javascript?

- Depends on Javascript
- Performance

### Why not use `-webkit-line-clamp` in chrome
- Need spec line-number
- Abandoned soon

## Usage

> Notice: use `.rtl.css` when applied in rtl page

#### single-line

```html
&lt;p class=&quot;text-overflow&quot; style=&quot;width: 100px;&quot;&gt;Bruna Marquezine e Giovanna Antonelli não param! Mesmo com o domingo.&lt;/p&gt;
```

#### multi-line

```html
&lt;div class="text-overflow-block" style="width: 100px; height: 200px;"&gt;
    &lt;p&gt;تكثف مباحث القليوبيه جهودها للقبض علي مسلحين اقتحموا كمين شرطه متحرك بمدخل مدينه العبور بطريق بلبيس الصحراوي، حيث قام الجناه بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات&lt;/p&gt;
&lt;/div&gt;
```

#### custom ellipsis

- Way 1, modify `.text-overflow-block:after`

```css
.text-overflow-block:after{ content: "xxxx";}
```

- Way 2, use built-in class: `text-overflow_end`

```css
.text-overflow-block:after{ display: none;}
.text-overflow_end{
    display: block;
    /* ... */
}
```

```html
&lt;div class="text-overflow-block" style="width: 100px; height: 200px;"&gt;
    &lt;p&gt;تكثف مباحث القليوبيه جهودها للقبض علي مسلحين اقتحموا كمين شرطه متحرك بمدخل مدينه العبور بطريق بلبيس الصحراوي، حيث قام الجناه بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات بفتح النار علي القوات عندما حاول افراده ايقافها للتفتيش دون اصابات، وتبادلت معهم القوات اطلاق الرصاص لكن المهاجمين فروا هاربين وتركوا السياره علي جانب الطريق، وكشفت المعاينه المبدئيه ان السياره مبلغ بسرقتها وبها اثار طلقات&lt;/p&gt;
    &lt;span class="text-overflow_end"&gt;&lt;a href="#"&gt;more&lt;/a&gt;&lt;/span&gt;
&lt;/div&gt;
```

## Issues

- The background color default set to white, modify it if the background color does not match