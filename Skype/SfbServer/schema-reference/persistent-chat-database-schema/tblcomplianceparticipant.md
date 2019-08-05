---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192747"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|channelUri  <br/> |Nvarchar (255), not null  <br/> |通道統一資源識別項 (URI)。  <br/> |
|userId  <br/> |int, not null  <br/> |參與者的主體識別碼 (對應至 tblPrincipal prinID 資料表)。  <br/> |
|joinedAt  <br/> |Bigint, not null  <br/> |加入事件的時間戳記。  <br/> |
|partedAt  <br/> |Bigint  <br/> |如果參與者仍在加入, 則為 Null。 如果 not null, 則通道的時間戳記會保留事件。  <br/> 這些專案會在所有翻譯員處理事件時最終移除。  <br/> |
|userUri  <br/> |Nvarchar (255), not null  <br/> |使用者 URI。  <br/> |
|serverID  <br/> |int  <br/> |伺服器身分識別 (例如在 serverID 資料表中則為 tblServerIdentity)。  <br/> |
|識別碼  <br/> |Bigint  <br/> |伺服器會話。 這是在每次聊天服務啟動時產生的亂數字。 它是用來區分會話, 目的是識別孤立參與者。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<channelUri、userId、joinedAt\>  <br/> |主鍵。  <br/> |
   

