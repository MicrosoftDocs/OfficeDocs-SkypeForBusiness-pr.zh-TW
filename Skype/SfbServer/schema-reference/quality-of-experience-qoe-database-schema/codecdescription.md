---
title: CodecDescription 表格
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表格會將唯一的轉碼器識別碼對應至它們對應的轉碼器。 轉碼器可用來為數位訊號編碼以利傳輸與廣播，然後將它們解碼以進行播放。 此表格已引進 Microsoft Lync Server 2013
ms.openlocfilehash: 8ef16503e1e28f3de478ef5593c990c4ce2e45dd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827356"
---
# <a name="codecdescription-table"></a>CodecDescription 表格
 
CodecDescription 表格會將唯一的轉碼器識別碼對應至它們對應的轉碼器。 轉碼器可用來為數位訊號編碼以利傳輸與廣播，然後將它們解碼以進行播放。 此表格已引進 Microsoft Lync Server 2013
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |Smallint  <br/> |主要  <br/> |指派給轉碼器的唯一識別碼。  <br/> |
|**CodecDescription** <br/> |Varchar (256)   <br/> |Unique  <br/> |對應至 CodecDescriptionKey 之轉碼器的唯一說明。  <br/> |
   

