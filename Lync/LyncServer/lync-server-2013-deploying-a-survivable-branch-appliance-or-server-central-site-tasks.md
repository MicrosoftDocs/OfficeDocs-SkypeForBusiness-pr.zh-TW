---
title: 部署 Survivable 分支裝置或伺服器中心網站工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced7b5262880b23540bf3465f787f6512781f2e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="6988f-102">使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-中央網站任務</span><span class="sxs-lookup"><span data-stu-id="6988f-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6988f-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6988f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6988f-104">在中央網站完成本節中的工作。</span><span class="sxs-lookup"><span data-stu-id="6988f-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="6988f-105">如果您要部署 Survivable 分支伺服器，請略過第一個任務。</span><span class="sxs-lookup"><span data-stu-id="6988f-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6988f-106">在您執行本節中的工作時，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="6988f-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6988f-107">必須在中央網站設定 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6988f-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="6988f-108">必須將分支網站的安裝技術人員加入至 RTCUniversalSBATechnicians 群組。</span><span class="sxs-lookup"><span data-stu-id="6988f-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="6988f-109">此外，我們建議您執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="6988f-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="6988f-110">在每個分支網站部署 DHCP 伺服器，讓用戶端能夠取得 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6988f-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="6988f-111">在每個分支網站上部署 DHCP 伺服器的替代方法，請使用 Lync Server Management Shell Cmdlet <STRONG>Set-get-csregistrarconfiguration –EnableDHCPServer $true</STRONG>，在 Survivable branch 裝置或 Survivable branch server 上啟用 LYNC server DHCP。</span><span class="sxs-lookup"><span data-stu-id="6988f-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="6988f-112">如需詳細資訊，請參閱規劃檔中的「適用于<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站恢復需求</A>」一節中的「硬體和軟體需求」一節。</span><span class="sxs-lookup"><span data-stu-id="6988f-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6988f-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6988f-113">In This Section</span></span>

  - [<span data-ttu-id="6988f-114">將 Survivable 分支裝置新增至 Active Directory 中的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6988f-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="6988f-115">將分支網站新增至您在 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="6988f-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="6988f-116">在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器</span><span class="sxs-lookup"><span data-stu-id="6988f-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

