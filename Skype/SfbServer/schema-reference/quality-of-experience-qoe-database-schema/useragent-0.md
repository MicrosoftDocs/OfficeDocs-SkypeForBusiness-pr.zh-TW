---
title: UserAgent view
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800013"
---
# <a name="useragent-view"></a>UserAgent view
 
UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |用於識別此使用者代理程式的唯一號碼。  <br/> |
|UserAgent  <br/> |Nvarchar (256)   <br/> |使用者代理程式字串。  <br/> |
|UAType  <br/> |Smallint  <br/> |使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|UACategory  <br/> |Nvarchar (64)   <br/> |使用者代理所屬的類別。 例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。  <br/> |
   

