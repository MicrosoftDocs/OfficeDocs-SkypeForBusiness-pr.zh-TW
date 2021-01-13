---
title: ClientVersions view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。 視圖中的每一筆記錄都代表一個用戶端版本。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813353"
---
# <a name="clientversions-view"></a>ClientVersions view
 
ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。 視圖中的每一筆記錄都代表一個用戶端版本。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> 某些欄可能會有多筆記錄。 
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |用於識別此用戶端類型及版本的唯一號碼。  <br/> |
|**版本** <br/> |Nvarchar (256)   <br/> |代表使用者代理程式。  <br/> |
|**ClientType** <br/> |int  <br/> |用戶端的類型。  <br/> |
|**ClientCategory** <br/> |Nvarchar (64)   <br/> |用戶端所屬的類別。 例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。  <br/> |
   

