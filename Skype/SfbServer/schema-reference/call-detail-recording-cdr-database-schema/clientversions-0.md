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
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。 視圖中的每一筆記錄都代表一個用戶端版本。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: bb17827f018919ba7b6088da884904a959bd6398
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593477"
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
   

