---
title: Lync Server 2013： 設定群組來電接聽
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
ms.openlocfilehash: cbd4c7fc1d0e2c052910b6ddcc9027b9c3db4f72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="4db46-102">在 Lync Server 2013 中設定群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="4db46-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4db46-103">_**上次修改主題：** 2013年-02-01_</span><span class="sxs-lookup"><span data-stu-id="4db46-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="4db46-104">Lync Server 2013 的累計更新： 2 月 2013年引進為新 Enterprise Voice 功能的群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="4db46-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="4db46-105">群組來電接聽可讓使用者揀選響鈴另一位使用者，撥出通話收取群組號碼的來電。</span><span class="sxs-lookup"><span data-stu-id="4db46-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="4db46-106">群組來電接聽使用的元件會自動安裝並啟用在前端伺服器或 Standard Edition 伺服器，當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="4db46-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="4db46-107">不過，您必須先設定群組來電接聽，再可供使用者。</span><span class="sxs-lookup"><span data-stu-id="4db46-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="4db46-108">本節會引導您完成群組來電接聽的組態。</span><span class="sxs-lookup"><span data-stu-id="4db46-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4db46-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4db46-109">In This Section</span></span>

[<span data-ttu-id="4db46-110">群組呼叫收取組態先決條件和 Lync Server 2013 中的使用者權限</span><span class="sxs-lookup"><span data-stu-id="4db46-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

<span data-ttu-id="4db46-111">[部署程序的 Lync Server 2013 中的 [群組來電接聽](lync-server-2013-deployment-process-for-group-call-pickup.md)</span><span class="sxs-lookup"><span data-stu-id="4db46-111">[Deployment process for Group Call Pickup in Lync Server 2013](lync-server-2013-deployment-process-for-group-call-pickup.md)</span></span>

[<span data-ttu-id="4db46-112">部署 Lync Server 2013 的 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="4db46-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="4db46-113">Lync Server 2013 中設定呼叫收取群組號碼</span><span class="sxs-lookup"><span data-stu-id="4db46-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="4db46-114">啟用群組來電接聽 Lync Server 2013 中的使用者並指派群組編號</span><span class="sxs-lookup"><span data-stu-id="4db46-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="4db46-115">通訊群組來電接聽指派給 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="4db46-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="4db46-116">（選用）確認 Lync Server 2013 中的群組來電接聽部署</span><span class="sxs-lookup"><span data-stu-id="4db46-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

