# Создание интерактивного объекта (Interactable)

> * Reading Time: 10 minutes
>
> * Checked with: Unity 2021.3.9f1

## Introduction

Данный гайд предназначен для создания интерактивного объекта (Interactable) на сцене. Данный объект возможно захватывать/отпускать (Grab/Ungrab), перемещать, кидать. 

## Let's Start

### Шаг 1

Создайте/добавьте объект на сцену, с которым хотите взаимодействовать, например `Cube`. Измените его размер через параметр `Scale` на `0.2`. Переместите его на возвышенное место (стол).

![Step 1](assets/images/_01_CreateCube.png)

![Step 1](assets/images/_01_ScaleCubee.png)

![Step 1](assets/images/_01_MoveCube.png)

### Шаг 2

Убедитесь, что у объекта есть коллайдер (`Box`, `Sphere`, `Cylinder` или `Mesh Collider`). 
Если он отсутствует у объекта, то добавьте новый компонент `Box Collider`. Для этого нажмите на кнопу `Add Component` в самом внизу окна `Inspector`. В поисковом поле введите `Box Collider` и выберите его из выпадающего списка ниже.

<details>
  <summary>	:red_circle: Mesh Collider 	:red_circle:</summary>
  Если у объекта имеется `Mesh Collider`, то убедитесь, что активен параметр `Convex` :ballot_box_with_check:.
  
![Step 1](assets/images/_01_Mesh.png)
</details>
<details>
  <summary>	:red_circle: Объект состоит из нескольких объектов 	:red_circle:</summary>
  Если у объекта имеются дочерние объекты, то нужно добавить на *каждый* объект с компонентом `Mesh Renderer` компонент `Mesh Collider`.
  
![Step 1](assets/images/_01_MeshRend.png)
</details>

![Step 1](assets/images/_01_Collider.png)