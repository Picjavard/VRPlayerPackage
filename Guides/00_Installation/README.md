# VR Player Package (Установка)

> * Reading Time: 10 minutes
>
> * Checked with: Unity 2022.3.50f1

## Introduction

VR Player Package основан на тулките VRTK v4.

Данный гайд посвящен быстрой настройке проекта для запуска на VR-шлеме (Oculus Quest 1/2 или HTC Vive).

VRPP содержит уже настроенный префаб игрока с 3D-симуляцией, плавным передвижением и системой захватом предметов.


## Let's Start

### Шаг 1

Создайте новый проект в Unity. Используйте шаблон `3D Core`.

![Step 1](assets/images/_1_Создание_проекта.png)

Для игрока нужен пол/платформа, который остановит игрока от падения вниз.
Поэтому создайте новый примитивный объект `Cube` выбрав `Main Menu -> GameObject -> 3D Object -> Cube` и измените параметры компонента `Transform`:

> * Position: `X = 0, Y = -0.5, Z = 0`
> * Scale: `X = 3, Y = 1, Z = 3`

Переименуйте `Cube`	`rgb(9, 105, 218)`на `Floor`.

![Step 1](assets/images/_1_floor.png)

Удалите `Main Camera` со сцены.

### Шаг 2

Скачайте и импортируйте в проект пакет `VR Player Package`. 

---> [VRPlayerPackage] <---

![Screenshot_30](https://github.com/user-attachments/assets/1abbc212-928a-4ba2-8bd1-b7f32126c4ed)
![Screenshot_31](https://github.com/user-attachments/assets/dcb7dacd-547e-423a-ad16-67ab5ae6d1cf)
![Screenshot_32](https://github.com/user-attachments/assets/0c9b0596-97f0-4c51-bf39-5ac15c23b94c)


Переместите на сцену префаб `Player`

![Screenshot_33](https://github.com/user-attachments/assets/266bb8fc-8c0e-48d3-827a-525e3d50c179)


Обратите внимание на ошибки в консоли (красный текст внизу экрана). Они говорят об отсутствии некоторых вложенных префабов у игрока (частей игрока), которые необходимо скачать/установить на следущем шаге.

### Шаг 3

Скачайте и импортируйте из Asset Store пакет `VRTK v4 Tilia Package Importer`. 

---> [vrtk-v4-tilia-package-importer] <---

![Step 4](assets/images/_8_TiliaDownload.png)
![Step 4](assets/images/_8_TiliaImport.png)

В диалоговом окне нажать `Install/Upgrade`.

![Step 4](assets/images/_8_UpgPackManager.png)

### Шаг 4

Откройте `Windows -> Tilia -> Package Importer` и нажмите на кнопку `Add Scoped Registry`. 

![Step 5](assets/images/_9_PImporter.png)
![Step 5](assets/images/_9_AddScoped.png)

Поставьте флажки напротив всех пакетов, кроме:

* `tilia.sdk.oculusintegration.unity`
* `tilia.sdk.picointegration.unity`
* `tilia.sdk.steamvr.unity`
* `tilia.sdk.wavexr.unity`

Нажмите на кнопку `Add Selected Packages`.

![Screenshot_34](https://github.com/user-attachments/assets/c36c8cc5-3384-4169-a20d-309d1bc10f2b)

Дождитесь окончания загрузки всех пакетов.

Появляется окно с предложением перейти на новую систему Input, выберите `Yes`, после чего проект перезагрузится.

![Screenshot_35](https://github.com/user-attachments/assets/249750aa-cda6-485c-b5a2-0595628f79ca)

Если до этого момента еще не сохраняли сцену, то появится еще одно окно, где нужно выбрать сохранение сцены

![Screenshot_36](https://github.com/user-attachments/assets/3fb4e7dc-30de-4919-828a-b62cb1fd5400)

В окне `Manage Unity InputManager Axis Definition` нажмите на кнопку `Add Input Definitions`.

![Step 5](assets/images/_11_Addinput.png)

Закройте плавающие окна, если такие есть.

### Шаг 5

Открыть настройки проекта `Edit -> Project Settings`. Перейти на `XR Plugin Management`. Поставить флажок напротив `Open XR`.

![Step 3](assets/images/_3_ProjectSettings.png) 
![Step 3](assets/images/_6_OpenXR.png)

После пройти `Edit -> Project Settings -> XR Plugin Management -> Project Validation` и нажать на `Fix All`. Дождитесь компиляции скриптов(два из трех желтых предупреждения исчезнут из списка).

![Screenshot_37](https://github.com/user-attachments/assets/5f9213f8-a6d1-43f0-be64-121f4ffb8ec1)

Нажмите у оставшегося предупреждения на кнопку `Edit` и создайте новый профайл взаимодействия, выбрав в `Interaction Profiles` `Oculus Touch Controller Profile` и/или `HTC Vive Controller Profile`

![Screenshot_38](https://github.com/user-attachments/assets/09248b6a-7cdb-41c0-94f7-77ba838fb3b8)
![Step 3](assets/images/_7_InterractionProfile.png)

## Готово

Нажмите на `Play`. В правом верхем углу окна `Game` появится интерфейс с кнопками `CameraRigs.SpatialSimulator` для запуска симуляции (клавиатура и мышь) и `CameraRigs.UnityXRPluginFramework` для запуска на подключенном к ПК VR-шлеме. 
	
> Если перед этим вы установили и настроили приложение `Oculus` для шлема `Oculus Quest 2` или `Steam VR` для шлема `HTC Vive`, то все запустится без проблем.
	
![Screenshot_40](https://github.com/user-attachments/assets/5b1f8fad-2623-40e8-bc67-1e96d67a1c96)

**Movement**

  `W` - Move current object forward.
 
  `A` - Move current object left.
 
  `S` - Move current object backward.
 
  `D` - Move current object right.
 
**Rotation**

 `Mouse` - Rotate current object up/down/left/right
 
 `Mouse Scroll Wheel` - Optional circular axis (e.g. mimics rotating finger around a trackpad).
 
**Buttons**

 `Left Mouse Button` - Can be used as button input.
 
 `Right Mouse Button` - Can be used as button input.
 
 `Middle Mouse Button` - Can be used as button input.
 
**Control**

 `1` - Activate movement/rotation of the simulated PlayArea and deactivate movement/rotation of simulated Controllers.
 
 `2` - Activate movement/rotation of the simulated Left Controller and deactivate movement/rotation of simulated PlayArea and Right Controller.
 
 `3` - Activate movement/rotation of the simulated Right Controller and deactivate movement/rotation of simulated PlayArea and Left Controller.
 
 `4` - Reset the position/rotation of the simulated PlayArea back to the default settings.
 
 `5` - Reset the position/rotation of the simulated Controllers back to the default settings.
 
 `6` - Lock/Unlock mouse cursor to Game window.
	
[Installation]: https://github.com/ExtendRealityLtd/Tilia.Indicators.ObjectPointers.Unity/blob/master/Documentation/HowToGuides/Installation/README.md
[vrtk-v4-tilia-package-importer]: https://assetstore.unity.com/packages/tools/utilities/vrtk-v4-tilia-package-importer-214936
[VRPlayerPackage]: assets/VRPlayerPackagePrefab/


