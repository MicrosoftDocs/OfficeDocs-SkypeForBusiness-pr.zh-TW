---
title: 商務用 Skype Server 2015 中的 Mcus 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表格是支援的表格。 每筆記錄儲存一筆會議服務的相關資訊。 這些可包含 IM 會議服務和電話語音會議服務 (，此服務會在前端伺服器上執行為處理常式) ，以及 Web 會議服務和 A/V 會議服務。
ms.openlocfilehash: 3cd0e096a09f1b83d50d4b7cad8428318d7fdb51
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416376"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 Mcus 表格
 
Mcus 表格是支援的表格。 每筆記錄儲存一筆會議服務的相關資訊。 這些可包含 IM 會議服務和電話語音會議服務 (，此服務會在前端伺服器上執行為處理常式) ，以及 Web 會議服務和 A/V 會議服務。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |主要  <br/> |用於識別此會議服務器的唯一號碼。  <br/> |
|**McuUri** <br/> |Nvarchar (450)   <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |會議服務器類型，例如會議： Im) 或會議：音訊-影片的聊天室 (。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
   

