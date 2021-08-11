---
title: 商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。 每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。
ms.openlocfilehash: 7e713e6d2eb9f856ee039345a0ab2e920e5ee09778b80201c823b14fbc270009
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289501"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
 
此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。 每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |會議執行個體的時間。 與 **SessionIdSeq** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |用於辨識執行個體的 ID 號碼。 與 **SessionIdTime** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |用於識別此使用者的唯一號碼，參考來源為 [ [使用者] 表格](users.md)。  <br/> |
|**MessageCount** <br/> |Smallint  <br/> | <br/> |此會議期間此使用者所傳送的訊息數。  <br/> |
   

