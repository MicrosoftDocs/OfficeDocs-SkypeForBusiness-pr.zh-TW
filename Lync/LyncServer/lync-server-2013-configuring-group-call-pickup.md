---
title: Lync Server 2013：設定群組呼叫挑選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d7f82d976d3e6e2594cecafe5634edfe0b52841
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="ed5ec-102">在 Lync Server 2013 中設定群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="ed5ec-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed5ec-103">_**主題上次修改日期：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="ed5ec-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="ed5ec-104">Lync Server 2013 的累積更新：2013年2月會將群組呼叫挑選引入為新的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="ed5ec-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="ed5ec-105">[群組通話挑選] 可讓使用者透過撥打電話挑選群組號碼來挑選撥打給其他使用者的通話。</span><span class="sxs-lookup"><span data-stu-id="ed5ec-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="ed5ec-106">當您部署企業語音時，會在前端伺服器或標準版伺服器上自動安裝並啟用群組呼叫拾取所用的元件。</span><span class="sxs-lookup"><span data-stu-id="ed5ec-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ed5ec-107">不過，您必須先設定 [群組呼叫挑選]，才能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="ed5ec-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="ed5ec-108">本節將引導您完成群組呼叫挑選的設定。</span><span class="sxs-lookup"><span data-stu-id="ed5ec-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed5ec-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="ed5ec-109">In This Section</span></span>

[<span data-ttu-id="ed5ec-110">Lync Server 2013 中的群組呼叫裝貨配置先決條件和使用者權利</span><span class="sxs-lookup"><span data-stu-id="ed5ec-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="ed5ec-111">Lync Server 2013 中群組呼叫挑選的部署程式</span><span class="sxs-lookup"><span data-stu-id="ed5ec-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="ed5ec-112">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="ed5ec-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="ed5ec-113">在 Lync Server 2013 中設定呼叫挑選群組號碼</span><span class="sxs-lookup"><span data-stu-id="ed5ec-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="ed5ec-114">在 Lync Server 2013 中為使用者啟用群組呼叫挑選，並指派群組號碼</span><span class="sxs-lookup"><span data-stu-id="ed5ec-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="ed5ec-115">在 Lync Server 2013 中將群組呼叫挑選指派給使用者</span><span class="sxs-lookup"><span data-stu-id="ed5ec-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="ed5ec-116">可選在 Lync Server 2013 中驗證群組呼叫裝貨部署</span><span class="sxs-lookup"><span data-stu-id="ed5ec-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

