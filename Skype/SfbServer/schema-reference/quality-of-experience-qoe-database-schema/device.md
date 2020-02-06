---
title: Device 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 資料表是一個支援資料表，可儲存各種捕獲或轉譯裝置的相關資訊。 資料表中的每一筆記錄代表一個裝置。
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810151"
---
# <a name="device-table"></a>Device 表格
 
Device 資料表是一個支援資料表，可儲存各種捕獲或轉譯裝置的相關資訊。 資料表中的每一筆記錄代表一個裝置。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |首選  <br/> |標識此裝置的唯一號碼。  <br/> |
|**DeviceName** <br/> |Nvarchar （256）  <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置名稱。  <br/> |
|**DeviceType** <br/> |稍微  <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置類型。 1是擷取裝置，0是轉譯裝置。  <br/> |
   

