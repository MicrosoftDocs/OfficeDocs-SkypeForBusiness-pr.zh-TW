---
title: IP 電話的 Lync Server 2013： 拓撲
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
ms.openlocfilehash: a1b01e4d98ced806b40cd5f092c0b8051ce86f47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="32e19-102">Lync Server 2013 中的 IP 電話的拓撲</span><span class="sxs-lookup"><span data-stu-id="32e19-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32e19-103">_**主題上次修改日期：** 2012年-06-21_</span><span class="sxs-lookup"><span data-stu-id="32e19-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="32e19-104">本節提供連線程序的概觀，並會說明 IP 電話連線至內部與外部網路的差異。</span><span class="sxs-lookup"><span data-stu-id="32e19-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32e19-105">Lync Server 支援下列的 IP 電話： Aastra 6721ip 公共區域電話、 Aastra 6725ip 電話機、 HP 4110 IP Phone （公共區域電話）、 HP 4120 IP 電話 （電話機）、 Polycom CX600 IP 電話機、 Polycom CX700 IP 電話機、 Polycom CX500 IP公共區域電話和 Polycom CX3000 IP 會議電話。</span><span class="sxs-lookup"><span data-stu-id="32e19-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="32e19-106">這些電話的所有但 Polycom CX700 可以執行 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="32e19-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="32e19-107">下圖說明公司環境中與裝置連線功能相關的所有元件。</span><span class="sxs-lookup"><span data-stu-id="32e19-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="32e19-108">**內部拓撲**</span><span class="sxs-lookup"><span data-stu-id="32e19-108">**Internal Topology**</span></span>

<span data-ttu-id="32e19-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="32e19-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32e19-110">上圖所呈現的是邏輯性代表，而不是實際的概觀。</span><span class="sxs-lookup"><span data-stu-id="32e19-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="32e19-111">例如，Active Directory 網域服務 (AD DS) 少位於任何 Lync Server 元件在同一部機器。</span><span class="sxs-lookup"><span data-stu-id="32e19-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="32e19-112">使用者存放區只能位於後端伺服器或是封存與監控伺服器之上。</span><span class="sxs-lookup"><span data-stu-id="32e19-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="32e19-113">Lync Server 管理命令介面、 網頁伺服器及更新服務都是屬於前端伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="32e19-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="32e19-114">下圖說明當裝置位於公司網路外時相關的元件概觀。</span><span class="sxs-lookup"><span data-stu-id="32e19-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="32e19-115">**外部拓撲**</span><span class="sxs-lookup"><span data-stu-id="32e19-115">**External Topology**</span></span>

<span data-ttu-id="32e19-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="32e19-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32e19-117">裝置更新 Web 服務會提供一個外部與內部網站，但此處僅顯示外部網站。</span><span class="sxs-lookup"><span data-stu-id="32e19-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="32e19-p103">當啟用外部存取時，組織的登錄器位置與裝置更新 Web 服務的 URL 都必須發佈至 DNS。此外，您必須部署並正確設定 Edge Server，以讓裝置和公司環境之間的外部通訊可順利進行。上圖省略了這個部分，因為 Edge 部署並不是專用於裝置連線此部分。</span><span class="sxs-lookup"><span data-stu-id="32e19-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

