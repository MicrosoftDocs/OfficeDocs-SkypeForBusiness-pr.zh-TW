---
title: Lync Server 2013： 為使用者啟用 E9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23df1bfce00baece3dce55d74497135863b26759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="1e97b-102">為使用者啟用 E9-1-1 在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e97b-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e97b-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="1e97b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="1e97b-104">在用戶端註冊期間 Lync Server 會使用位置原則來設定已啟用 Enterprise Voice 的使用者的 E9-1-1 屬性。</span><span class="sxs-lookup"><span data-stu-id="1e97b-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="1e97b-105">此原則包含的設定會定義 E9-1-1 實作方式。</span><span class="sxs-lookup"><span data-stu-id="1e97b-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="1e97b-106">例如，「 位置原則包含資訊，例如緊急撥號對應表的字串，而不論使用者必須手動輸入位置，如果將位置資訊服務不會自動提供一。</span><span class="sxs-lookup"><span data-stu-id="1e97b-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="1e97b-107">位置原則的完整定義，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1e97b-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="1e97b-108">Lync Server 可以指派位置原則，子網路為基礎的用戶端或使用者根據全域、 每個網站或個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="1e97b-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="1e97b-109">如需判斷該如何啟用使用者，請先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="1e97b-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="1e97b-110">**您打算啟用所有使用者，還是打算將支援範圍限定在企業的特定地理區域？**</span><span class="sxs-lookup"><span data-stu-id="1e97b-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="1e97b-111">您可以使用通用位置原則，將某個位置指派給企業中所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="1e97b-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="1e97b-112">不過，藉由將位置原則指派給 Lync Server 網路網站，並再將子網路新增至網站，您可以限制 E9-1-1 支援在企業內的選取位置，並指定 E9-1-1 的路由傳送行為以每個網站為基礎。</span><span class="sxs-lookup"><span data-stu-id="1e97b-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="1e97b-113">**您是否打算透過使用者原則啟用個別使用者？**</span><span class="sxs-lookup"><span data-stu-id="1e97b-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="1e97b-114">如果您想自訂使用者的 E9-1-1 支援，可以直接指派位置原則給特定使用者或公共區域電話連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="1e97b-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="1e97b-115">**當用戶端漫遊至網路外，或從未定義的子網路連線時，是否仍應啟用用戶端的 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="1e97b-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="1e97b-116">如果使用者指派全域、 網站，或個別使用者位置原則，他們可能需要手動輸入到用戶端的位置，如果用戶端不是位於內定義的子網路或位置資訊服務已找到任何位置。</span><span class="sxs-lookup"><span data-stu-id="1e97b-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="1e97b-117">如需詳細資訊，請參閱[定義手動取得位置 Lync Server 2013 中的使用者經驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="1e97b-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

