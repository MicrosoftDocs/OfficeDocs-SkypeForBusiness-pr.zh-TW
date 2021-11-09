---
title: 商務用 Skype Server 2015 中的 CallType 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 7f00e924041c5b26f7045cf8f97ae82daa141611
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845086"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallType 表格
 
CallType 表格是儲存可能通話類型清單的靜態表格。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |主要  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || 允許的值： <br/>  0 -- 不明 <br/>  1-立即訊息 <br/>  2--應用程式共用 <br/>  3--音訊 <br/>  4-音訊和影片 <br/>  5-檔案傳輸 <br/> |
   

