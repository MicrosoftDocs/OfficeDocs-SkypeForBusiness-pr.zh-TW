---
title: ProgressReport 視圖
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: '[ProgressReport] 視圖儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814981"
---
# <a name="progressreport-view"></a>ProgressReport 視圖
 
[ProgressReport] 視圖儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。 
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |發生錯誤的時間。 與 ErrorReportSeq 搭配使用，可唯一識別錯誤。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |識別錯誤的識別碼號碼。 與 ErrorTime 搭配使用，可唯一識別錯誤。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |標識進度報表的識別碼。 用來區分相同錯誤報表的進度報告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |錯誤報表的診斷 ID。  <br/> |
|**從源** <br/> |Nvarchar （256）  <br/> |產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。  <br/> |
|**應用程式** <br/> |Nvarchar （256）  <br/> |產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |特定元件加入會議所需的時間（以毫秒為單位）。  <br/> |
|**MsDiagHeader** <br/> |Varchar （max）  <br/> |其他錯誤資訊。  <br/> |
   

