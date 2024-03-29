---
title: 監視商務用 Skype Server 2015 中的 IIS 要求追蹤記錄檔
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要：瞭解 Mcx) 中的行動服務 (的商務用 Skype Server 2015 支援舊版用戶端。
ms.openlocfilehash: a2331d4f18488171b1862e53f06f4910b463ccb5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396555"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>監視商務用 Skype Server 2015 中的 IIS 要求追蹤記錄檔
 
**總結：** 深入瞭解 Mcx) 中的行動服務 (商務用 Skype Server 2015 支援舊版用戶端。
  
本主題僅適用于支援 Lync 2010 Lync 行動用戶端的部署，且適用于行動服務 (Mcx) 。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
當您為商務用 Skype Server 行動服務 (Mcx) 啟用 Internet Information Services (IIS) 要求追蹤時，所產生的記錄檔會每日消耗最多三 gb 的磁碟空間。 預設會啟用 IIS 追蹤記錄。 您應該監視前端伺服器，確定其磁碟空間不足。 
  
根據預設，IIS 會將記錄檔儲存在%SystemDrive%\inetpub\logs\LogFiles。
  
若要關閉整個伺服器的 IIS 要求追蹤，請在命令列輸入下列命令：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

如需 **HTTPLogging** 命令的詳細資訊，請參閱 [命令參考](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。
