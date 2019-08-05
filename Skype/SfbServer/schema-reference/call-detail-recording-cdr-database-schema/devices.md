---
title: 商務用 Skype Server 2015 中的 [裝置] 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: '[裝置] 資料表是支援資料表。 每筆記錄儲存一個裝置 (電話機) 的相關資訊。'
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192874"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 [裝置] 表格
 
[裝置] 資料表是支援資料表。 每筆記錄儲存一個裝置 (電話機) 的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |首選  <br/> |識別這個硬體版本的唯一號碼。  <br/> |
|**[Manufacturerid** <br/> |int  <br/> |外  <br/> |此裝置的製造商。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](manufacturers.md)的 [製造商] 資料表。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外  <br/> |此裝置的硬體版本。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](hardwareversions.md)的 [HardwareVersions] 資料表。 <br/> |
|**MacAddress** <br/> |Bigint  <br/> ||MAC 位址  <br/> |
   

