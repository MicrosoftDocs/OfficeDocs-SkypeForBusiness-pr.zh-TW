---
title: 商務用 Skype Server 2015 中的 CallType 表格
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表格是儲存可能通話類型清單的靜態表格。
ms.openlocfilehash: 7c84e245cac2ceb25a5012f9caf4a2a31d4cb67b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620909"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallType 表格
 
CallType 表格是儲存可能通話類型清單的靜態表格。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |主要  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || 允許的值： <br/>  0 -- 不明 <br/>  1-立即訊息 <br/>  2--應用程式共用 <br/>  3--音訊 <br/>  4-音訊和影片 <br/>  5-檔案傳輸 <br/> |
   

