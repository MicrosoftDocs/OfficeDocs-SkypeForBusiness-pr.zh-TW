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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: '[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805081"
---
# <a name="useragent-view"></a>UserAgent 視圖
 
[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |標識此使用者代理程式的唯一號碼。  <br/> |
|UserAgent  <br/> |Nvarchar （256）  <br/> |使用者代理程式字串。  <br/> |
|UAType  <br/> |Smallint  <br/> |使用者代理程式類型。 如需詳細資訊，請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|UACategory  <br/> |Nvarchar （64）  <br/> |使用者代理所屬的類別。 例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。  <br/> |
   

