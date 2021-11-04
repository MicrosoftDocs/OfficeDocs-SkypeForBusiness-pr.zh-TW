---
title: ProgressReport view
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport view 儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 42229b0a756b6ed30c9736f4b97e0d00a653565e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767471"
---
# <a name="progressreport-view"></a>ProgressReport view
 
ProgressReport view 儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> [ErrorTime]、[ErrorReportSeq] 和 [ProgressReportSeq] 欄位不一定會參考錯誤，而是指出來電或郵件狀態的訊息。 
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |發生錯誤的時間。 與 ErrorReportSeq 搭配使用，以唯一識別錯誤。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |用以識別錯誤的 ID 號碼。 與 ErrorTime 搭配使用，以唯一識別錯誤。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |識別進度報表的識別碼。 用來區分相同錯誤報表的進度報告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |錯誤報表的診斷識別碼。  <br/> |
|**Source** <br/> |Nvarchar (256)   <br/> |起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。  <br/> |
|**應用程式** <br/> |Nvarchar (256)   <br/> |起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。  <br/> |
|**TelemetryId** <br/> |唯一  <br/> |與會議相關聯之不同元件的加入時間資訊的唯一識別碼。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |特定元件加入會議所需的時間 (（毫秒）) 。  <br/> |
|**MsDiagHeader** <br/> |Varchar (max)   <br/> |其他錯誤資訊。  <br/> |
   

