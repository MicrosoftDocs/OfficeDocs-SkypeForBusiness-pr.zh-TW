---
title: 商務用 Skype Server 2015 的裝置表格
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表格是一種支援資料表。每筆記錄儲存一部裝置 (電話機) 的資訊。
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的裝置表格
 
Devices 表格是一種支援資料表。每筆記錄儲存一部裝置 (電話機) 的資訊。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |主要  <br/> |用於識別此硬體版本的唯一號碼。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |此裝置的製造商。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的製造商表格](manufacturers.md)。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |此裝置的硬體版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 HardwareVersions 表格](hardwareversions.md)。 <br/> |
|**MacAddress** <br/> |Bigint  <br/> ||MAC 位址  <br/> |
   

