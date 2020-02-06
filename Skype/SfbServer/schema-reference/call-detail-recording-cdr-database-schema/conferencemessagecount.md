---
title: 商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此資料表中的每筆記錄代表一個 IM 會議中的一位使用者，包括該使用者所傳送的訊息數目。 每個會議都是由這個表格中的多筆記錄所代表;每個使用者一個記錄。
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815371"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
 
此資料表中的每筆記錄代表一個 IM 會議中的一位使用者，包括該使用者所傳送的訊息數目。 每個會議都是由這個表格中的多筆記錄所代表;每個使用者一個記錄。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會議實例的時間。 與**SessionIdSeq**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會議實例的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |外  <br/> |標識此使用者的唯一編號，從 [[使用者] 資料表](users.md)中引用。  <br/> |
|**MessageCount** <br/> |Smallint  <br/> | <br/> |此使用者在此會議期間傳送的訊息數目。  <br/> |
   

