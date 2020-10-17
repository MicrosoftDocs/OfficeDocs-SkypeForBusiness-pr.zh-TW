---
title: 設定語音原則、PSTN 使用方式記錄和語音路由
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
ms.openlocfilehash: 0e749419cf84303cfef9d4718488a4483adecb97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537000"
---
# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="6c885-102">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="6c885-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c885-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="6c885-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="6c885-p101">語音原則、PSTN 使用方式記錄和語音路由密切相關。您可以選取一組撥號功能，接著指派一組 PSTN 使用方式記錄給原則，以便指定獲指派語音原則的使用者或群組可獲得哪些權限授權，如此就能設定語音原則。語音路由也會被指派 PSTN 使用方式記錄，這些記錄會用來比對路由與獲授權使用這些路由的使用者。也就是說，使用者可以撥打的電話，只限於使用他們有相符 PSTN 使用方式記錄之路由的電話。</span><span class="sxs-lookup"><span data-stu-id="6c885-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="6c885-108">新 Enterprise Voice 部署的建議工作流程是：從設定包含適當 PSTN 使用方式記錄的語音原則開始，接著將適當路由關聯給每個 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="6c885-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6c885-109">您也可以在「<EM>使用者</EM>」範圍建立語音原則，然後將其指派給個別使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6c885-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="6c885-110">如需執行每項工作的詳細步驟，請參閱本節程序。</span><span class="sxs-lookup"><span data-stu-id="6c885-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c885-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6c885-111">In This Section</span></span>

  - [<span data-ttu-id="6c885-112">在 Lync Server 2013 中設定語音原則和 PSTN 使用方式記錄，以授權呼叫功能和許可權</span><span class="sxs-lookup"><span data-stu-id="6c885-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="6c885-113">在 Lync Server 2013 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="6c885-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="6c885-114">在 Lync Server 2013 中設定撥出電話的語音路由</span><span class="sxs-lookup"><span data-stu-id="6c885-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="6c885-115">在 Lync Server 2013 中匯出及匯入語音路由設定</span><span class="sxs-lookup"><span data-stu-id="6c885-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="6c885-116">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="6c885-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="6c885-117">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="6c885-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

