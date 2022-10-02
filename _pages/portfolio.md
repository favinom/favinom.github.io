---
layout: archive # category
title: Simulation portfolio
permalink: /portfolio/
author_profile: true
---

### Thermoelasticity equations for a cooktop

Thermoelasticity equations are employed to simulate the deformation of a cooktop
during its heating process.
Deformations can be relatively large and can make cooktop's surface not flat.
As a consequence, pots will not adhere to the surface and energetic efficiency of the cooktop
may be affected.

In this project, we simulated cooktop's deformations.
The geometry employed is a realistic one from an industrial partner.
It features three wires that make three rounds over the vertical axis.

Thermoelasticty equations have been implemented both in **UG** and **FreeFem++**.

<img src="/assets/section001.png" alt="mesh_front" width="310"/>
<img src="/assets/top001.png" alt="mesh_back" width="310"/>

<img src="/assets/section002.png" alt="mesh_front" width="310"/>
<img src="/assets/top002.png" alt="mesh_back" width="310"/>

<img src="/assets/section004.png" alt="mesh_front" width="310"/>
<img src="/assets/top004.png" alt="mesh_back" width="310"/>

<img src="/assets/section006.png" alt="mesh_front" width="310"/>
<img src="/assets/top006.png" alt="mesh_back" width="310"/>

<img src="/assets/section008.png" alt="mesh_front" width="310"/>
<img src="/assets/top008.png" alt="mesh_back" width="310"/>

<img src="/assets/section009.png" alt="mesh_front" width="310"/>
<img src="/assets/top009.png" alt="mesh_back" width="310"/>

<img src="/assets/section010.png" alt="mesh_front" width="310"/>
<img src="/assets/top010.png" alt="mesh_back" width="310"/>

<img src="/assets/section012.png" alt="mesh_front" width="310"/>
<img src="/assets/top012.png" alt="mesh_back" width="310"/>



### Poroelasticity equations in dental biomechanics

The periodontal ligament (PDL) is a soft connective tissue that attaches a tooth to the alveolar bone.
The PDL is mainly composed of collagene fibers and an interstitial fluid.
Understanding the mechanical response in both physiological and pathological cases
is fundamental for the early detection of PDL diseases, like the parodontisis.

To take into accont the biphasic composition of the PDL
and the large deformations that may occur in the PDL ,
nonlinear Biot's equations of poroelasticity are employed.
Moreover, fine meshes are necessary to accurately represents the complicated geometrical structure of the PDL.

Below, you see the mesh of a two-root porcine tooth-PDL system.
<img src="/assets/mesh_front.pdf" alt="mesh_front" width="200"/>
<img src="/assets/mesh_back.pdf" alt="mesh_back" width="200"/>

The mesh of the PDL is colored in blue,
while the mesh of the tooth is in pink.
In red, we report the surface on which
the external displacement is imposed
and the reaction force is measured.

In order to simulate the indentation experiments on the tooth,
we have implemented a coupled elastic-poroelastic model in the software **UG**.
The tooth is modeled as an elastic body,
while the PDL as a poroelastic bosy.

In the figures below, we report the boundary stressed resulting from the application
of an external displacement (Dirichlet boundary conditions) of 0.1 mm (left)
and of 0.2 mm (right).
<img src="/assets/front10.pdf" alt="mesh_front" width="300"/>
<img src="/assets/front20.pdf" alt="mesh_back" width="300"/>


In the figures below, we report the pressure distribution in the PDL
due to the imposition external displacement (Dirichlet boundary conditions) of 0.1 mm (left)
and of 0.2 mm (right).
<img src="/assets/back10.pdf" alt="mesh_front" width="300"/>
<img src="/assets/back20.pdf" alt="mesh_back" width="300"/>





Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
