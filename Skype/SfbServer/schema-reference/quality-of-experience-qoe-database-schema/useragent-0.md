---
title: UserAgent 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: '[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192623"
---
# <a name="useragent-view"></a>UserAgent 視圖
 
[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |標識此使用者代理程式的唯一號碼。  <br/> |
|UserAgent  <br/> |Nvarchar (256)  <br/> |使用者代理程式字串。  <br/> |
|UAType  <br/> |Smallint  <br/> |使用者代理程式類型。 如需詳細資訊, 請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|UACategory  <br/> |Nvarchar (64)  <br/> |使用者代理所屬的類別。 例如, 使用者代理程式 Conferencing_Attendant_ 1.0 屬於 UACategory CAA。  <br/> |
   

