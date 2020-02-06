---
title: 商務用 Skype 中監控 IIS 要求的追蹤記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要：瞭解商務用 Skype Server 2015 支援舊版用戶端的行動服務（Mcx）。
ms.openlocfilehash: 982e5842499e5cb2f6ff21ff884d1baa45075627
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817923"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>商務用 Skype 中監控 IIS 要求的追蹤記錄檔
 
**摘要：** 瞭解商務用 Skype Server 2015 支援舊版用戶端的行動服務（Mcx）。
  
本主題僅適用于支援 Lync 2010 Lync Mobile 用戶端的部署，且適用于行動服務（Mcx）。

> [!NOTE]
> MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
當您針對商務用 Skype Server 行動服務（Mcx）啟用 Internet Information Services （IIS）要求追蹤時，產生的記錄檔案每天最多可以消耗 3 gb 的磁碟空間。 預設會啟用 IIS 追蹤記錄。 您應該監視前端伺服器，以確保它們不會耗盡磁碟空間。 
  
根據預設，IIS 會將記錄檔儲存在%SystemDrive%\inetpub\logs\LogFiles。
  
若要關閉整個伺服器的 IIS 要求追蹤，請在命令列中輸入下列內容：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

如需**HTTPLogging**命令的詳細資訊，請參閱[命令參考](https://go.microsoft.com/fwlink/p/?linkId=234927)。
  

