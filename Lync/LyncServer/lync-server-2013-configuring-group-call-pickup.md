---
title: Lync Server 2013：設定群組呼叫收取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b994415be41abe0f534f4120b2411b1f6b9beb0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517414"
---
# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="fa24e-102">在 Lync Server 2013 中設定群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="fa24e-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa24e-103">_**主題上次修改日期：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="fa24e-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="fa24e-104">Lync Server 2013 的累計更新：2月2013將群組呼叫收取引進為新的 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="fa24e-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="fa24e-105">群組呼叫收取可讓使用者透過撥打呼叫收取群組號碼來挑選撥打給另一位使用者的通話。</span><span class="sxs-lookup"><span data-stu-id="fa24e-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="fa24e-106">當您部署企業語音時，會自動在前端伺服器或 Standard Edition server 上安裝並啟用群組呼叫收取所使用的元件。</span><span class="sxs-lookup"><span data-stu-id="fa24e-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fa24e-107">不過，您必須先設定群組呼叫收取，使用者才能使用它。</span><span class="sxs-lookup"><span data-stu-id="fa24e-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="fa24e-108">本節會引導您完成群組呼叫收取設定。</span><span class="sxs-lookup"><span data-stu-id="fa24e-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa24e-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="fa24e-109">In This Section</span></span>

[<span data-ttu-id="fa24e-110">Lync Server 2013 中的群組呼叫收取設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="fa24e-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="fa24e-111">Lync Server 2013 中群組呼叫收取的部署程式</span><span class="sxs-lookup"><span data-stu-id="fa24e-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="fa24e-112">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="fa24e-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="fa24e-113">在 Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="fa24e-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="fa24e-114">為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼</span><span class="sxs-lookup"><span data-stu-id="fa24e-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="fa24e-115">在 Lync Server 2013 中通訊群組呼叫收取指派給使用者</span><span class="sxs-lookup"><span data-stu-id="fa24e-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="fa24e-116"> (選用) 驗證 Lync Server 2013 中的群組呼叫收取部署</span><span class="sxs-lookup"><span data-stu-id="fa24e-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

