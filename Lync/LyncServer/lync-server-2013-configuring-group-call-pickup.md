---
title: Lync Server 2013：設定群組呼叫收取
description: Lync Server 2013：設定群組呼叫收取。
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
ms.openlocfilehash: ff6be1ea20a98cfaf2addf32c7767940b420c5c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575909"
---
# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="64738-103">在 Lync Server 2013 中設定群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="64738-103">Configuring Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64738-104">_**主題上次修改日期：** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="64738-104">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="64738-105">Lync Server 2013 的累計更新：2月2013將群組呼叫收取引進為新的 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="64738-105">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="64738-106">群組呼叫收取可讓使用者透過撥打呼叫收取群組號碼來挑選撥打給另一位使用者的通話。</span><span class="sxs-lookup"><span data-stu-id="64738-106">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="64738-107">當您部署企業語音時，會自動在前端伺服器或 Standard Edition server 上安裝並啟用群組呼叫收取所使用的元件。</span><span class="sxs-lookup"><span data-stu-id="64738-107">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="64738-108">不過，您必須先設定群組呼叫收取，使用者才能使用它。</span><span class="sxs-lookup"><span data-stu-id="64738-108">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="64738-109">本節會引導您完成群組呼叫收取設定。</span><span class="sxs-lookup"><span data-stu-id="64738-109">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="64738-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="64738-110">In This Section</span></span>

[<span data-ttu-id="64738-111">Lync Server 2013 中的群組呼叫收取設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="64738-111">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="64738-112">Lync Server 2013 中群組呼叫收取的部署程式</span><span class="sxs-lookup"><span data-stu-id="64738-112">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="64738-113">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="64738-113">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="64738-114">在 Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="64738-114">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="64738-115">為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼</span><span class="sxs-lookup"><span data-stu-id="64738-115">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="64738-116">在 Lync Server 2013 中通訊群組呼叫收取指派給使用者</span><span class="sxs-lookup"><span data-stu-id="64738-116">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="64738-117"> (選用) 驗證 Lync Server 2013 中的群組呼叫收取部署</span><span class="sxs-lookup"><span data-stu-id="64738-117">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

