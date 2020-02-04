---
title: Lync Server 2013：擷取位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="b6667-102">在 Lync Server 2013 中擷取位置</span><span class="sxs-lookup"><span data-stu-id="b6667-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6667-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b6667-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b6667-104">在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端都會主動取得自己的位置。</span><span class="sxs-lookup"><span data-stu-id="b6667-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="b6667-105">在 SIP 註冊之後，用戶端會在位置資訊服務（由複製的 SQL Server 資料庫支援的 web 服務）的位置要求中，furnishes 它知道的所有網路連線資訊。</span><span class="sxs-lookup"><span data-stu-id="b6667-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="b6667-106">每個中央網站池都有一個位置資訊服務，該服務會使用網路資訊來查詢其記錄中的相符位置。</span><span class="sxs-lookup"><span data-stu-id="b6667-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="b6667-107">如果有相符專案，位置資訊服務會傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="b6667-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="b6667-108">如果沒有相符的專案，系統可能會提示使用者手動輸入位置（視位置原則設定而定）。</span><span class="sxs-lookup"><span data-stu-id="b6667-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="b6667-109">位置資料會以網際網路工程任務組（IETF）標準化 XML 格式傳回用戶端，稱為「目前狀態資訊資料格式位置」物件（PIDF-LO）。</span><span class="sxs-lookup"><span data-stu-id="b6667-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="b6667-110">Lync Server 用戶端會在緊急通話中包含 PIDF-LO 資料，而 E9 1-1 服務提供者會使用此資料來判斷適當的 PSAP，並將呼叫傳送給該 PSAP 以及正確的 ESQK，這可讓 PSAP dispatcher 取得來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="b6667-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="b6667-111">下圖顯示 Lync Server 用戶端如何取得位置（除了協力廠商用戶端 MAC 位址的位置方法之外）：</span><span class="sxs-lookup"><span data-stu-id="b6667-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="b6667-112">![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端如何取得位置圖表")</span><span class="sxs-lookup"><span data-stu-id="b6667-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="b6667-113">若要讓用戶端取得位置，必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b6667-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="b6667-114">系統管理員會使用 network wiremap （將各種類型的網路位址對應至相對應緊急回應位置（ERLs））來填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="b6667-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="b6667-115">如果您使用 SIP 幹線 E9-1 服務提供者，系統管理員會針對由 E9-1 服務提供者所維護的主要街道位址指南（MSAG）資料庫，驗證 ERLs 的市政位址部分。</span><span class="sxs-lookup"><span data-stu-id="b6667-115">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="b6667-116">如果您使用的是 ELIN 閘道，系統管理員會確保 PSTN 載波將 ELINs 上傳到自動位置識別（阿裡）資料庫。</span><span class="sxs-lookup"><span data-stu-id="b6667-116">If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="b6667-117">在註冊期間或每當網路變更時，內部連接的用戶端會傳送包含用戶端探索之網路位址的位置要求給位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="b6667-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="b6667-118">位置資訊服務會針對某個位置查詢其已發佈的記錄，如果找到一個相符專案，則會以 PIDF 格式傳回用戶端的 ERL。</span><span class="sxs-lookup"><span data-stu-id="b6667-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

