---
title: Lync Server 2013： 取得位置
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
ms.openlocfilehash: 7e726424e9e24c223bc7e75346bd0c2188f29ee7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="99a07-102">取得 Lync Server 2013 中的位置</span><span class="sxs-lookup"><span data-stu-id="99a07-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99a07-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="99a07-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="99a07-104">在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端主動取得它自己的位置。</span><span class="sxs-lookup"><span data-stu-id="99a07-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="99a07-105">SIP 註冊後，用戶端提供它所知本身其位置要求中的位置資訊服務，也就是由複寫的 SQL Server 資料庫的 web 服務的所有網路連線資訊。</span><span class="sxs-lookup"><span data-stu-id="99a07-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="99a07-106">每個中央網站集區有位置資訊服務，它會使用網路資訊來查詢比對的位置記錄。</span><span class="sxs-lookup"><span data-stu-id="99a07-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="99a07-107">如果沒有相符項目，位置資訊服務會傳回給用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="99a07-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="99a07-108">如果不相符項目，可能會提示使用者輸入位置，以手動方式 （根據位置原則 」 設定）。</span><span class="sxs-lookup"><span data-stu-id="99a07-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="99a07-109">位置資料傳送回至名為目前狀態資訊的資料格式位置物件 (PIDF-LO) 的用戶端中網際網路工程任務推動小組 (IETF) 標準化 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="99a07-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="99a07-110">Lync Server 用戶端中包含 PIDF-LO 資料一部分緊急通話，並用此資料 E9-1-1 服務提供者來決定適當的 PSAP，並路由傳送至該 PSAP 連同正確的 esqk 一起，可讓 PSAP 調度員得以取得來電發話者的位置。</span><span class="sxs-lookup"><span data-stu-id="99a07-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="99a07-111">下圖顯示 Lync Server 用戶端如何取得位置 （但不包括第三方用戶端 MAC 位址型方法）：</span><span class="sxs-lookup"><span data-stu-id="99a07-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="99a07-112">![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端如何取得位置圖表")</span><span class="sxs-lookup"><span data-stu-id="99a07-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="99a07-113">若要取得位置用戶端，必須執行下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="99a07-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="99a07-114">由系統管理員將網路線路圖 （將各種網路位址對應至對應的緊急事故回應位置 (Erl) 的表格） 的位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="99a07-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="99a07-115">如果您使用 SIP 主幹 E9-1-1 服務提供者時，系統管理員會驗證針對 E9-1-1 服務提供者所維護的主要街道地址指南 (MSAG) 資料庫的 Erl 市街地址部分。</span><span class="sxs-lookup"><span data-stu-id="99a07-115">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="99a07-116">如果您使用 ELIN 閘道時，系統管理員可確保，PSTN 電信業者會將上傳 Elin 到自動位置識別 (ALI) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="99a07-116">If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="99a07-117">凡是登錄或網路變更發生時，內部連線用戶端會傳送位置要求，其中包含用戶端被發現的位置資訊服務的網路位址。</span><span class="sxs-lookup"><span data-stu-id="99a07-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="99a07-118">位置資訊服務查詢已發行的記錄位置，並如果找到相符項目，就會傳回 ERL 給用戶端以 PIDF-LO 格式。</span><span class="sxs-lookup"><span data-stu-id="99a07-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

