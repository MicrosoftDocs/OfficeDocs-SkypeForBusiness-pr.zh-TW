---
title: 裝置表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。
ms.openlocfilehash: d060ec010cc67ea45fb2f7c58ccc574a7bdbc4ea566342943f7a8f587a9676f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347728"
---
# <a name="device-table"></a>裝置表格
 
Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |主要  <br/> |用於識別此裝置的唯一號碼。  <br/> |
|**DeviceName** <br/> |Nvarchar (256)   <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置名稱。  <br/> |
|**DeviceType** <br/> |位  <br/> |DeviceName + DeviceType 是唯一的  <br/> |裝置類型。 1是捕獲裝置，0代表呈現裝置。  <br/> |
   

