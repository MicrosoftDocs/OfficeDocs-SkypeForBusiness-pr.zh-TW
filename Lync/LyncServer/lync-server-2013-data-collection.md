---
title: Lync Server 2013：資料收集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="13a68-102">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="13a68-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13a68-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="13a68-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="13a68-104">在 Microsoft Lync Server 2013 通訊軟體中，您可以執行 Microsoft Lync Server 2013、規劃工具，而不需記錄現有和建議的 IP 位址及 Edge 伺服器的完整功能變數名稱（Fqdn），但是這樣做很難所以不會造成設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="13a68-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="13a68-105">例如，如果在一段時間內需要共存，常見的錯誤是從您的 Lync Server 2013 Edge 部署的現有 Edge 部署重複使用 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="13a68-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="13a68-106">您可以在試算表、表格或其他視覺形式中，將現有與提議的 IP 位址及 Fqdn 寫下，以協助避免在安裝期間發生設定問題。</span><span class="sxs-lookup"><span data-stu-id="13a68-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="13a68-107">如果您使用的是舊版的規劃工具，您可能已經使用工具來建立拓撲，以及匯出拓撲結構檔以供在拓撲產生器中使用，發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="13a68-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="13a68-108">已從規劃工具中移除匯出拓撲的功能。</span><span class="sxs-lookup"><span data-stu-id="13a68-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="13a68-109">我們強烈建議您使用舊版的規劃工具來建立 Lync Server 2013 的拓撲檔，並產生不預期的結果。</span><span class="sxs-lookup"><span data-stu-id="13a68-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="13a68-110">因此，建議的方法是使用下列資料收集範本（對應到您的邊緣拓撲），收集您需要在規劃工具中輸入的各種 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="13a68-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="13a68-111">透過記錄目前與建議的設定，您可以將值放在您生產環境的適當內容中。</span><span class="sxs-lookup"><span data-stu-id="13a68-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="13a68-112">而且，您會強行考慮如何設定共存與功能，例如簡單的 Url、檔案共用及負載平衡。</span><span class="sxs-lookup"><span data-stu-id="13a68-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="13a68-113">若要成功部署 Microsoft Lync Server 2013，您必須瞭解個別元件的互動與依賴性。</span><span class="sxs-lookup"><span data-stu-id="13a68-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="13a68-114">您可以從現有的網路和伺服器基礎結構中收集資料，並在這些區段中套用規劃指南，就能將 Lync Server 2013 Edge 伺服器元件整合到您的基礎結構中。</span><span class="sxs-lookup"><span data-stu-id="13a68-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="13a68-115">在[Lync Server 2013 選擇拓撲](lync-server-2013-choosing-a-topology.md)中引入，有三種主要的體系結構，有兩種變化，共五種可能的部署案例。</span><span class="sxs-lookup"><span data-stu-id="13a68-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="13a68-116">您的資料收集起點就是其中一種案例。</span><span class="sxs-lookup"><span data-stu-id="13a68-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="13a68-117">IP 位址、伺服器名稱和功能變數名稱是與相符的憑證、防火牆和 DNS 圖表相符的範例，詳細說明完整規劃方案所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="13a68-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="13a68-118">規劃圖並填入您所需的憑證，DNS 和防火牆值在跨小組通訊中尤為重要，在這種情況下，管理憑證授權單位、防火牆設定和 DNS 由團隊以外的小組所管理規劃部署。</span><span class="sxs-lookup"><span data-stu-id="13a68-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="13a68-119">圖表會提供必要元件的相關資訊，這些元件可用於傳達這些需求以進行跨團隊共同作業。</span><span class="sxs-lookup"><span data-stu-id="13a68-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="13a68-120">所提供的圖表是特意通用的，但可讓您在跨團隊案例中的需求（在網路、防火牆、證書建立與管理、伺服器部署和伺服器管理是由不同的群組來處理。</span><span class="sxs-lookup"><span data-stu-id="13a68-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="13a68-121">在進行 Lync Server 的部署時，擁有網路、防火牆、埠和通訊協定、證書及伺服器的設定所需的詳細資料是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="13a68-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="13a68-122">**Edge 伺服器與邊緣池**</span><span class="sxs-lookup"><span data-stu-id="13a68-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="13a68-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="13a68-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="13a68-124">**反向 Proxy**</span><span class="sxs-lookup"><span data-stu-id="13a68-124">**Reverse Proxy**</span></span>

<span data-ttu-id="13a68-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="13a68-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="13a68-126">**主管或主管池**</span><span class="sxs-lookup"><span data-stu-id="13a68-126">**Director or Director pool**</span></span>

<span data-ttu-id="13a68-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="13a68-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

