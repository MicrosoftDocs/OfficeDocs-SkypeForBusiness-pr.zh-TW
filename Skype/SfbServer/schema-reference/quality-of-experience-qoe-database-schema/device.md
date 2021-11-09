---
title: 裝置表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。
ms.openlocfilehash: e999cf493cce69ee05d8a342e346cf8277d8d5d8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827416"
---
# <a name="device-table"></a>裝置表格
 
Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |主要  <br/> |用於識別此裝置的唯一號碼。  <br/> |
|**DeviceName** <br/> |Nvarchar (256)   <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置名稱。  <br/> |
|**DeviceType** <br/> |位  <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置類型。 1是捕獲裝置，0代表呈現裝置。  <br/> |
   

