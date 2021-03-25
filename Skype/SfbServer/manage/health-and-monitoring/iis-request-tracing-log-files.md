---
title: 在商務用 Skype Server 2015 中監控 IIS 要求的追蹤記錄檔
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要：瞭解適用于舊版用戶端的商務用 Skype Server 2015 支援的行動服務 (Mcx) 。
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118632"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中監控 IIS 要求的追蹤記錄檔
 
**摘要：** 瞭解適用于舊版用戶端的商務用 Skype Server 2015 支援的行動服務 (Mcx) 。
  
本主題僅適用于支援 Lync 2010 Lync 行動用戶端的部署，且適用于行動服務 (Mcx) 。

> [!NOTE]
> MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。 所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
當您為商務用 Skype Server 行動服務 (Mcx) 啟用 Internet Information Services (IIS) 要求追蹤時，所產生的記錄檔可能會消耗最多三 gb 的磁碟空間。 預設會啟用 IIS 追蹤記錄。 您應該監視前端伺服器，確定其磁碟空間不足。 
  
根據預設，IIS 會將記錄檔儲存在%SystemDrive%\inetpub\logs\LogFiles。
  
若要關閉整個伺服器的 IIS 要求追蹤，請在命令列輸入下列命令：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

如需 **HTTPLogging** 命令的詳細資訊，請參閱 [命令參考](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。
