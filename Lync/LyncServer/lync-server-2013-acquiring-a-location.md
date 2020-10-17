---
title: Lync Server 2013：取得位置
description: Lync Server 2013：取得位置。
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
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571109"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="58ef6-103">在 Lync Server 2013 中取得位置</span><span class="sxs-lookup"><span data-stu-id="58ef6-103">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ef6-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="58ef6-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="58ef6-105">在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端都會主動取得自己的位置。</span><span class="sxs-lookup"><span data-stu-id="58ef6-105">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="58ef6-106">在 SIP 註冊後，用戶端會將其本身所知道的所有網路連線資訊 furnishes 至位置資訊服務（即複製的 SQL Server 資料庫所支援的 web 服務）的位置要求。</span><span class="sxs-lookup"><span data-stu-id="58ef6-106">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="58ef6-107">每個中央網站集區都有一個位置資訊服務，可使用網路資訊來查詢其記錄中的相符位置。</span><span class="sxs-lookup"><span data-stu-id="58ef6-107">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="58ef6-108">如果有相符的位置資訊服務會將位置傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="58ef6-108">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="58ef6-109">如果不符合，系統會提示使用者手動輸入位置 (，視位置原則設定) 而定。</span><span class="sxs-lookup"><span data-stu-id="58ef6-109">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="58ef6-110">位置資料會傳回網際網路工程工作中的用戶端。 (的 IETF) 標準化 XML 格式，稱為目前狀態資訊資料格式位置物件 (PIDF-LO) 。</span><span class="sxs-lookup"><span data-stu-id="58ef6-110">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="58ef6-111">Lync Server 用戶端在緊急通話過程中包含 PIDF-LO 資料，而 E9-1-1 服務提供者會使用此資料來判斷適當的 PSAP，並將通話路由傳送至該 PSAP，也就是正確的 ESQK 一起，讓 PSAP dispatcher 可以取得來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="58ef6-111">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="58ef6-112">下圖顯示 Lync Server 用戶端如何取得位置 (，但不包括協力廠商用戶端 MAC 位址型位置方法) ：</span><span class="sxs-lookup"><span data-stu-id="58ef6-112">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="58ef6-113">![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端如何取得位置圖表")</span><span class="sxs-lookup"><span data-stu-id="58ef6-113">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="58ef6-114">若要讓用戶端取得位置，必須進行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="58ef6-114">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="58ef6-115">系統管理員會以網路線路圖將各種網路位址對應至對應緊急回應位置（ (Erl) # A3）的 [網路] (表格，填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="58ef6-115">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="58ef6-116">如果您使用 SIP 主幹 E9-1-1 服務提供者，則系統管理員會依照主要街道位址指南 (MSAG) E9-1-1 服務提供者所維護的資料庫來驗證 Erl 的市政位址部分。</span><span class="sxs-lookup"><span data-stu-id="58ef6-116">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="58ef6-117">如果您使用的是 ELIN 閘道，則系統管理員會確保 PSTN 載波將 Elin 上傳至自動位置識別 (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="58ef6-117">If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="58ef6-118">在註冊期間或網路變更發生時，內部連線的用戶端會傳送包含用戶端已探索網路位址的位置要求至位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="58ef6-118">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="58ef6-119">位置資訊服務會查詢其發佈的記錄的位置，如果找到相符的記錄，則會以 PIDF-LO 格式將 ERL 傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="58ef6-119">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

