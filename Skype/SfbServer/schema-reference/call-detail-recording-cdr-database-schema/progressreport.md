---
title: ProgressReport 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 進度報告是以通話或工作階段完成時，用戶端上傳至資料庫的資料為基礎。 進度報告只會寫入商務用 Skype Server 2015 所決定的呼叫和會話，以供診斷之用。
ms.openlocfilehash: 969b6ca08461483857015123a2b90303654435d2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404565"
---
# <a name="progressreport-table"></a>ProgressReport 表格
 
進度報告是以通話或工作階段完成時，用戶端上傳至資料庫的資料為基礎。 進度報告只會寫入商務用 Skype Server 2015 所決定的呼叫和會話，以供診斷之用。
  
[ErrorTime]、[ErrorReportSeq] 和 [ProgressReportSeq] 欄位不一定會參考錯誤，而是指出來電或郵件狀態的訊息。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主要，外部  <br/> |包含此進度報告之進度錯誤報告的日期和時間。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ErrorReport 表格](errorreport.md)。 <br/> |
|**ErrorId** <br/> |int  <br/> |主要，外部  <br/> |與 ErrorTime、ProgressReportSeq 搭配使用的識別碼，可識別唯一的進度報告。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ErrorReport 表格](errorreport.md)。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主要，外部  <br/> |識別錯誤報告的識別碼。 ErrorReporSeq 與 ErrorTime 搭配使用，可識別唯一的錯誤報告。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ErrorReport 表格](errorreport.md) <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |主要  <br/> |用於識別進度報告的識別碼。與 ErrorTime 及 ErrorReportSeq 搭配使用，可識別唯一的進度報告。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||進度報告的診斷 ID。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |傳送錯誤報表的伺服器 (如果報告是從伺服器元件傳送) 。 如需詳細資訊，請參閱 [Servers 表格](servers.md) 。此欄位是在 Microsoft Lync Server 2013 中引入的。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||報告針對的 Lync Server 程序。如需詳細資訊，請參閱應用程式表格。  <br/> |
|**Detail** <br/> |image  <br/> ||進度報告詳細資料，以二進位格式儲存，以節省空間。可使用此語法將資料轉換成文字格式：  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |唯一  <br/> ||會議所包含之不同元件的加入時間資訊的相互關聯唯一識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定元件加入會議的時間 (毫秒)。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

