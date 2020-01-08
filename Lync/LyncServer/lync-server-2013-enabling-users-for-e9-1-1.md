---
title: Lync Server 2013：啟用 E9-1-1 版使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="196e3-102">在 Lync Server 2013 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="196e3-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="196e3-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="196e3-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="196e3-104">在用戶端註冊期間，Lync Server 會使用位置原則來設定企業語音使用者的 E9 屬性。</span><span class="sxs-lookup"><span data-stu-id="196e3-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="196e3-105">此原則包含定義如何執行 E9-1-1 的設定。</span><span class="sxs-lookup"><span data-stu-id="196e3-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="196e3-106">例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="196e3-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="196e3-107">如需位置原則的完整定義，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="196e3-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="196e3-108">Lync Server 可以根據子網來指派位置策略給客戶，或是根據全域、每個網站或每個使用者的原則，指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="196e3-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="196e3-109">若要協助您決定將如何啟用使用者，您應該先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="196e3-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="196e3-110">**您是否計畫要啟用所有使用者，或限制對企業特定地理區域的支援？**</span><span class="sxs-lookup"><span data-stu-id="196e3-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="196e3-111">您可以使用全域位置原則，將位置指派給企業中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="196e3-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="196e3-112">不過，若要將位置原則指派給 Lync Server 網路網站，然後將子網新增至網站，您可以將 E9-1-1 支援限制在企業內所選的位置，並在每個網站上指定 E9 的路由行為。</span><span class="sxs-lookup"><span data-stu-id="196e3-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="196e3-113">**您是否計畫透過使用者原則啟用個別使用者？**</span><span class="sxs-lookup"><span data-stu-id="196e3-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="196e3-114">如果您想要自訂 E9-1-1 支援，您可以將位置原則直接指派給特定的使用者或常見的區域電話連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="196e3-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="196e3-115">**當用戶端在網路外部漫遊或從未定義的子網進行連線時，如果用戶端仍在 E9-1-1，就應該啟用用戶端嗎？**</span><span class="sxs-lookup"><span data-stu-id="196e3-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="196e3-116">如果將使用者指派為全域、網站或每位使用者的位置原則，當用戶端不在已定義的子網中，或位置資訊服務找不到任何位置時，可能需要他們手動在用戶端中輸入位置。</span><span class="sxs-lookup"><span data-stu-id="196e3-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="196e3-117">如需詳細資訊，請參閱[定義在 Lync Server 2013 中手動取得位置的使用者體驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="196e3-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

