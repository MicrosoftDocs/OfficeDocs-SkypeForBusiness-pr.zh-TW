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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="588d5-103">商務用 Skype 中監控 IIS 要求的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="588d5-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="588d5-104">**摘要：** 瞭解商務用 Skype Server 2015 支援舊版用戶端的行動服務（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="588d5-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="588d5-105">本主題僅適用于支援 Lync 2010 Lync Mobile 用戶端的部署，且適用于行動服務（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="588d5-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="588d5-106">MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="588d5-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="588d5-107">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="588d5-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="588d5-108">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="588d5-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="588d5-109">當您針對商務用 Skype Server 行動服務（Mcx）啟用 Internet Information Services （IIS）要求追蹤時，產生的記錄檔案每天最多可以消耗 3 gb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="588d5-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="588d5-110">預設會啟用 IIS 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="588d5-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="588d5-111">您應該監視前端伺服器，以確保它們不會耗盡磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="588d5-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="588d5-112">根據預設，IIS 會將記錄檔儲存在%SystemDrive%\inetpub\logs\LogFiles。</span><span class="sxs-lookup"><span data-stu-id="588d5-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="588d5-113">若要關閉整個伺服器的 IIS 要求追蹤，請在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="588d5-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="588d5-114">如需**HTTPLogging**命令的詳細資訊，請參閱[命令參考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="588d5-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

