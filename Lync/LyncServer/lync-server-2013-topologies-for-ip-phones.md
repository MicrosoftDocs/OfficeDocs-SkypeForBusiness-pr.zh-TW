---
title: Lync Server 2013： IP 手機的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="5b99b-102">Lync Server 2013 中的 IP 手機拓撲</span><span class="sxs-lookup"><span data-stu-id="5b99b-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b99b-103">_**主題上次修改日期：** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="5b99b-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="5b99b-104">本節概述連接程式，並說明 IP 電話在內部和外部網路中的連線方式之間的差異。</span><span class="sxs-lookup"><span data-stu-id="5b99b-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b99b-105">Lync Server 提供下列 IP 電話支援： Aastra 6721ip 常見區域手機、Aastra 6725ip phone、HP 4110 IP Phone （通用區域電話）、HP 4120 IP phone （常見地區電話）、Polycom CX600 IP Phone （電話機），以及 Polycom CX700 ip 電話機、Polycom CX500 IP常見的區域電話，以及 Polycom CX3000 IP 會議電話。</span><span class="sxs-lookup"><span data-stu-id="5b99b-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="5b99b-106">在這些手機中，除了 Polycom CX700 之外，所有人都可以執行 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="5b99b-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="5b99b-107">下圖說明公司環境中所有裝置連線所涉及的元件。</span><span class="sxs-lookup"><span data-stu-id="5b99b-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="5b99b-108">**內部拓朴**</span><span class="sxs-lookup"><span data-stu-id="5b99b-108">**Internal Topology**</span></span>

<span data-ttu-id="5b99b-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="5b99b-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b99b-110">上圖是邏輯標記法，不是物理概覽。</span><span class="sxs-lookup"><span data-stu-id="5b99b-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="5b99b-111">例如，Active Directory 網域服務（AD DS）很少位於與任何 Lync Server 元件相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="5b99b-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="5b99b-112">使用者存放區可以位於後端伺服器或 [封存與監視伺服器] 上。</span><span class="sxs-lookup"><span data-stu-id="5b99b-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="5b99b-113">Lync Server 管理命令介面、web 伺服器及更新服務全都是前端伺服器角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="5b99b-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="5b99b-114">下圖提供裝置位於公司網路以外時所涉及元件的概覽。</span><span class="sxs-lookup"><span data-stu-id="5b99b-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="5b99b-115">**外部拓撲**</span><span class="sxs-lookup"><span data-stu-id="5b99b-115">**External Topology**</span></span>

<span data-ttu-id="5b99b-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="5b99b-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b99b-117">裝置更新 Web 服務提供外部與內部網站，但此處只顯示外部網站。</span><span class="sxs-lookup"><span data-stu-id="5b99b-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="5b99b-118">如果要啟用外部存取，則必須在 DNS 中發佈註冊機構的裝置更新 Web 服務的位置和 URL。</span><span class="sxs-lookup"><span data-stu-id="5b99b-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="5b99b-119">此外，還必須部署並正確設定 Edge 伺服器，才能允許從裝置到公司環境的外部通訊和返回。</span><span class="sxs-lookup"><span data-stu-id="5b99b-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="5b99b-120">這會在前一個圖表中省略，因為 Edge 部署不是特定于裝置連線性的。</span><span class="sxs-lookup"><span data-stu-id="5b99b-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

