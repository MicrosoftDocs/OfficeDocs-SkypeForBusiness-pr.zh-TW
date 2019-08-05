---
title: ClientVersions 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192899"
---
# <a name="clientversions-view"></a>ClientVersions 視圖
 
ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> 某些欄可能有多個記錄。 
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |標識此用戶端類型與版本的唯一號碼。  <br/> |
|**版本** <br/> |Nvarchar (256)  <br/> |代表使用者代理程式。  <br/> |
|**ClientType** <br/> |int  <br/> |用戶端類型。  <br/> |
|**ClientCategory** <br/> |Nvarchar (64)  <br/> |用戶端所屬的類別。 例如, 用戶端 Conferencing_Attendant_ 1.0 屬於 ClientCategory CAA。  <br/> |
   

