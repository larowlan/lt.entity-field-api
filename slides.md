# Drupal <img src="images/d8-logo.png" alt="Drupal 8 logo" width="100" style="background:none; border:none; margin: 0; box-shadow: none">

## Entity Field API for developers

Lee Rowlands

<larowlan@previousnext.com.au>

[@larowlan](https://twitter.com/larowlan)

---

## What are you talking about?

- You know this stuff<!-- .element: class="fragment" data-fragment-index="1" -->
```php
$node->field_make_it_stop['LANGUAGE_NONE'][0]['wtf_bbq'];
```
<!-- .element: class="fragment" data-fragment-index="1" -->
- In Drupal 8 the pain ends<!-- .element: class="fragment" data-fragment-index="2" -->
```php
$node->field_rainbows->value;
$node->title->value;
```
<!-- .element: class="fragment" data-fragment-index="2" -->
- Today we're talking about the magic sauce<!-- .element: class="fragment" data-fragment-index="3" -->

---

## Disclaimer

- This is my understanding
- Your mileage may vary

Note:

- Credits to berdir, fago, plach, andypost, yched

---

## The key interfaces

Also known as _meet your new friends_

--

## The key interfaces

1. EntityInterface<!-- .element: class="fragment" data-fragment-index="1" -->
2. ContentEntityInterface<!-- .element: class="fragment" data-fragment-index="2" -->
3. FieldItemListInterface<!-- .element: class="fragment" data-fragment-index="3" -->
4. FieldItemInterface<!-- .element: class="fragment" data-fragment-index="4" -->

--

## EntityInterface

- The base point
- 2 kindsa <del>love</del> entities
- Config (another day)
- Content

--

## ContentEntityInterface

- Starting point for nodes, users, taxonomy etc
- ContentEntityBase

--

## FieldItemListInterface

- What you get here<!-- .element: class="fragment" data-fragment-index="1" -->
```php
$this_is_a_field_item_list = $node->field_rainbows
```
<!-- .element: class="fragment" data-fragment-index="1" -->
- Methods<!-- .element: class="fragment" data-fragment-index="2" -->
    - getEntity()<!-- .element: class="fragment" data-fragment-index="3" -->
    - getFieldDefinition()<!-- .element: class="fragment" data-fragment-index="4" -->
    - getSetting()<!-- .element: class="fragment" data-fragment-index="5" -->
    - Magic getters/setters<!-- .element: class="fragment" data-fragment-index="6" -->
    ```php
    $this_is_a_field_item_list->value
    ```
    <!-- .element: class="fragment" data-fragment-index="6" -->
- Extends from TypedData\ListInterface (a whole other topic...)<!-- .element: class="fragment" data-fragment-index="7" -->
- Much much more<!-- .element: class="fragment" data-fragment-index="8" -->

--

## FieldItemInterface

- What you get here<!-- .element: class="fragment" data-fragment-index="1" -->
```php
$this_is_a_field_item = $node->field_rainbows->get($index)
```
<!-- .element: class="fragment" data-fragment-index="1" -->
- Methods<!-- .element: class="fragment" data-fragment-index="2" -->
    - getProperties()<!-- .element: class="fragment" data-fragment-index="3" -->
    - getFieldDefinition()<!-- .element: class="fragment" data-fragment-index="4" -->
    - getEntity()<!-- .element: class="fragment" data-fragment-index="5" -->
    - Magic getters/setters<!-- .element: class="fragment" data-fragment-index="6" -->
    ```php
    $this_is_a_field_item_list->get(0)->entity
    ```
    <!-- .element: class="fragment" data-fragment-index="6" -->
- Extends from TypedData\ComplexDataInterface (a whole other topic...)<!-- .element: class="fragment" data-fragment-index="7" -->


Note:

- $node->field_item->value internally chains via this to the first one in list

---

# Questions?

---

## Thank you!

<larowlan@previousnext.com.au>

[@larowlan](https://twitter.com/larowlan)
