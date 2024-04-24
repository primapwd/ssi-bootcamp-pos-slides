---
theme: light-icons
layout: intro
author: Prima Putra
image: https://images.unsplash.com/photo-1489710437720-ebb67ec84dd2
title: Point of Sales (POS)
hideInToc: true
# drawings:
#   persist: false
transition: slide-left
fonts:
  sans: 'Nunito'
  mono: 'Fira Code'
highlighter: shiki
---

<div class="mb-4 absolute top-8 left-12">
  <span class="text-4xl text-primary-lighter text-opacity-60" style="font-weight:500;" >
    Mini Bootcamp <light-icon icon="device-desktop"/>
  </span>
  <div class="text-7xl text-white text-opacity-90" style="font-weight:600;" >
    Point Of Sales (POS)
  </div> 
</div>

<!--
Left for comment
-->

---
theme: light-icons
transition: slide-left
title: Introduction
class: 'list-none'
zoom: 1.5
hideInToc: true
---

# Introduction

<div class="mt-8">
  <ul class="list-none">
    <li><solar-user-id-bold /> <span class="font-bold text-lg">Prima Putra W.</span></li>
    <li><solar-buildings-bold /> <span class="underline">Senior Software Developer</span> at <span class="font-bold">Solusi Sistem Informasi (SSI)</span></li>
    <li><ph-game-controller-fill /> Futsal, Gaming, Coding & Build Stuff</li>
  </ul>
</div>

<!--
Here is another comment.
-->

---
transition: slide-up
title: What To Do?
layout: center
zoom: 1.5
hideInToc: true
---

# What will we build?

<!-- Another comment -->

---
theme: light-icons
layout: center
transition: slide-up
title: Point Of Sales
hideInToc: true
---

# Point Of Sales
<!-- Put ending product image here -->

---
transition: slide-up
clicks: 1
hideInToc: true
---

# Topics

<div>
  <ul class="list-none">
    <li><span v-mark.box.orange><ph-users-bold /> User & Permission <span>(1<sup>st</sup> Day)</span></span></li>
    <li><solar-box-bold /> Master Barang etc <span>(2<sup>nd</sup> Day)</span></li>
    <li><ph-cash-register /> Point of Sales (Cashier) <span>(3<sup>rd</sup> Day)</span> </li>
    <li><solar-notebook-bookmark-bold /> Reporting <span>(4<sup>th</sup> Day)</span></li>
    <li><solar-card-linear /> Payment Gateway <span>(4<sup>th</sup> Day)</span> 🤔</li>
  </ul>
</div>

---
title: Today's Activities
hideInToc: true
---

# Today's Activities

<Toc />

---
layout: center
zoom: 1.4
title: Installation & Setup (30m)
---

# Installation & Setup

```sh {1|2|3}
$ composer create-project laravel/laravel pos
$ cd pos
$ php artisan serve
```

---
layout: center-image
image: './images/ss1.png'
hideInToc: true
---


---
layout: two-cols
layoutClass: gap-8
title: Slicing Template & Login (30m)
---

# Slicing Template & Login

* <span v-mark.box.orange>Copy js, css & fonts</span>
* <span v-mark.box.orange>Install Laravel Breeze</span>
  * <span v-mark.box.orange> `composer require laravel/breeze --dev` </span>
  * <span v-mark.box.orange> `php artisan breeze:install` </span>
  * <span v-mark.box.orange> `php artisan db:seed` </span>
* <span v-mark.box.orange> Copy & buat file layout </span>
  * <span v-mark.box.orange> Ubah app.blade.php </span>
  * <span v-mark.box.orange> Copy _navbar.blade.php </span>
  * <span v-mark.box.orange> Copy _sidebar.blade.php </span>
  * <span v-mark.box.orange> Ubah dashboard.blade.php </span>

::right::

<img src="/public/images/ss2.png" v-click class="rounded shadow" />

---
title: Build Users Management (40m)
---

# Build Users Management

* <span v-mark.box.orange>Buat Resource Route untuk User Management</span>
  * <span v-mark.box.orange>`php artisan make:controller UsersController -rR --model=User`</span>
* <span v-mark.box.orange>Tambahkan route ke web.php</span>
  * <span v-mark.box.orange>`Route::resource('users', App\Http\Controllers\UsersController::class);`</span>

---
title: Build Users Management #2 (40m)
hideInToc: true
---

# Build Users Management

```sh
routes/web.php
```

````md magic-move
```php
Route::middleware('auth')->group(function () {
    Route::get('/profile', [ProfileController::class, 'edit'])->name('profile.edit');
    Route::patch('/profile', [ProfileController::class, 'update'])->name('profile.update');
    Route::delete('/profile', [ProfileController::class, 'destroy'])->name('profile.destroy');
});
```
```php {6|*}
Route::middleware('auth')->group(function () {
    Route::get('/profile', [ProfileController::class, 'edit'])->name('profile.edit');
    Route::patch('/profile', [ProfileController::class, 'update'])->name('profile.update');
    Route::delete('/profile', [ProfileController::class, 'destroy'])->name('profile.destroy');

    Route::resource('users', App\Http\Controllers\UsersController::class);
});
```
````


---
title: Build Users Management #3 (40m)
hideInToc: true
---

# Build Users Management

* <span v-mark.box.orange>Ubah link di sidebar</span>
* <span v-mark.box.orange>Buat file blade untuk index, tambah & edit</span>

---
title: Build Permission Management (40m)
---

# Build Permission Management

---
layout: center
class: text-center
hideInToc: true
---

# 🙏🏻 Thank you! 😊

# See you next session 😉
