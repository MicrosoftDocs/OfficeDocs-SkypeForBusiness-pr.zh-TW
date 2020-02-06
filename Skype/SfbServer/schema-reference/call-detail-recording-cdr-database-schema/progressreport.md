---
title: ProgressReport 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 進度報告是以用戶端在通話或會話完成後上傳到資料庫的資料為基礎。 進度報告將只會撰寫給商務用 Skype Server 2015 判斷的通話和會話，對於診斷用途可能很有用。
ms.openlocfilehash: a6cd89d7ba7f8cc03b25dc9310bdb408c85b50cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814971"
---
# <a name="progressreport-table"></a>ProgressReport 表格
 
進度報告是以用戶端在通話或會話完成後上傳到資料庫的資料為基礎。 進度報告將只會撰寫給商務用 Skype Server 2015 判斷的通話和會話，對於診斷用途可能很有用。
  
ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主要、外部  <br/> |包含此進度報告之進度錯誤報表的日期和時間。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](errorreport.md)的 [ErrorReport] 資料表。 <br/> |
|**ErrorId** <br/> |int  <br/> |主要、外部  <br/> |與 ErrorTime、ProgressReportSeq 搭配使用的識別碼編號，可唯一識別進度報告。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](errorreport.md)的 [ErrorReport] 資料表。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主要、外部  <br/> |識別錯誤報表的識別碼編號。 ErrorReporSeq 與 ErrorTime 搭配使用，可唯一識別錯誤報表。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](errorreport.md)的 [ErrorReport] 資料表 <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |首選  <br/> |識別進度報表的識別碼編號。 與 ErrorTime 和 ErrorReportSeq 搭配使用，可唯一識別進度報告。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||進度報告的診斷識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**源** <br/> |int  <br/> |外  <br/> |傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。 如需詳細資訊，請參閱 [[伺服器] 資料表](servers.md)。此欄位是在 Microsoft Lync Server 2013 中推出。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||報告所用的 Lync Server 進程。 如需詳細資訊，請參閱應用程式表格。  <br/> |
|**具體** <br/> |影像  <br/> ||以二進位格式儲存的進度報告詳細資料，以節省空間。此資料可以使用下列語法轉換成文字格式：  <br/> cast （以 Varbinary （max）格式轉換為 Varchar （max））  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定元件加入會議所需的時間（以毫秒為單位）。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

