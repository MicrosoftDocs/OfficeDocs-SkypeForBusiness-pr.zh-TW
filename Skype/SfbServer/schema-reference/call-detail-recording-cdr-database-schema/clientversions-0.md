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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815411"
---
# <a name="clientversions-view"></a>ClientVersions 視圖
 
ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> 某些欄可能有多個記錄。 
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |標識此用戶端類型與版本的唯一號碼。  <br/> |
|**版本** <br/> |Nvarchar （256）  <br/> |代表使用者代理程式。  <br/> |
|**ClientType** <br/> |int  <br/> |用戶端類型。  <br/> |
|**ClientCategory** <br/> |Nvarchar （64）  <br/> |用戶端所屬的類別。 例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。  <br/> |
   

