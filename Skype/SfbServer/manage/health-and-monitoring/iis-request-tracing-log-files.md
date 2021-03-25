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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="78aca-103">在商務用 Skype Server 2015 中監控 IIS 要求的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="78aca-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78aca-104">**摘要：** 瞭解適用于舊版用戶端的商務用 Skype Server 2015 支援的行動服務 (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="78aca-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="78aca-105">本主題僅適用于支援 Lync 2010 Lync 行動用戶端的部署，且適用于行動服務 (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="78aca-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="78aca-106">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="78aca-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="78aca-107">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="78aca-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="78aca-108">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="78aca-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="78aca-109">當您為商務用 Skype Server 行動服務 (Mcx) 啟用 Internet Information Services (IIS) 要求追蹤時，所產生的記錄檔可能會消耗最多三 gb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="78aca-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="78aca-110">預設會啟用 IIS 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="78aca-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="78aca-111">您應該監視前端伺服器，確定其磁碟空間不足。</span><span class="sxs-lookup"><span data-stu-id="78aca-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="78aca-112">根據預設，IIS 會將記錄檔儲存在%SystemDrive%\inetpub\logs\LogFiles。</span><span class="sxs-lookup"><span data-stu-id="78aca-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="78aca-113">若要關閉整個伺服器的 IIS 要求追蹤，請在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="78aca-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="78aca-114">如需 **HTTPLogging** 命令的詳細資訊，請參閱 [命令參考](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="78aca-114">For details about the **httpLogging** command, see [the command reference](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).</span></span>
