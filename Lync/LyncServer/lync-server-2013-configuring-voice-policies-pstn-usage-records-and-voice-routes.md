---
title: 設定語音原則、PSTN 使用記錄及語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="6c9c2-102">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="6c9c2-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c9c2-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="6c9c2-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="6c9c2-104">語音原則、PSTN 使用記錄及語音路由都是 integrally 相關的。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-104">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="6c9c2-105">您可以透過選取一組通話功能來設定語音原則，然後將原則指派給一組 PSTN 使用記錄，指定將哪些權利授權給指派了語音原則的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-105">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="6c9c2-106">語音路由也是指派 PSTN 使用記錄，可讓路由與有權使用它們的使用者相符。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-106">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="6c9c2-107">也就是說，使用者只能將使用路由的呼叫放在其中，他們有相符的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-107">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="6c9c2-108">新企業語音部署的建議工作流程是從設定包含適當 PSTN 使用記錄的語音原則開始，然後將適當的路由與每個 PSTN 使用量記錄產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6c9c2-109">您也可以使用<EM>使用者</EM>範圍建立語音原則，並將其指派給個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="6c9c2-110">如需執行每項工作的詳細步驟，請參閱本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="6c9c2-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c9c2-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="6c9c2-111">In This Section</span></span>

  - [<span data-ttu-id="6c9c2-112">在 Lync Server 2013 中設定用於授權撥號功能和權限的語音原則和 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="6c9c2-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="6c9c2-113">在 Lync Server 2013 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="6c9c2-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="6c9c2-114">Lync Server 2013 中設定撥出電話的語音路由</span><span class="sxs-lookup"><span data-stu-id="6c9c2-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="6c9c2-115">在 Lync Server 2013 中匯出和匯入語音路由組態</span><span class="sxs-lookup"><span data-stu-id="6c9c2-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="6c9c2-116">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="6c9c2-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="6c9c2-117">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="6c9c2-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

