---
title: Lync Server 2013 支援的集區配對選項及最佳作法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 963f1532ca7a1aa5402a54936909a22727ab9716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="ac23a-102">支援的集區配對選項和 Lync Server 2013 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ac23a-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac23a-103">_**主題上次修改日期：** 2017年-03-09_</span><span class="sxs-lookup"><span data-stu-id="ac23a-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="ac23a-p101">將要包含與彼此配對之前端集區的兩個資料中心之間，並沒有距離的限制。建議您在相同的地區設定中使用兩個資料中心，彼此以高速連結。兩個資料中心最好分隔得夠遠，以避免單一災害同時衝擊到兩個資料中心。</span><span class="sxs-lookup"><span data-stu-id="ac23a-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="ac23a-107">擁有跨地理區域的兩個資料中心是可行的，但是可能會因為資料複寫延遲，而導致資料遺失的風險較高。</span><span class="sxs-lookup"><span data-stu-id="ac23a-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="ac23a-108">當您規劃哪些集區配對時，您必須記住，只有下列配對受支援：</span><span class="sxs-lookup"><span data-stu-id="ac23a-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="ac23a-p102">Enterprise Edition 集區只能與其他 Enterprise Edition 集區配對。同樣地，Standard Edition 集區只能與其他 Standard Edition 集區配對。</span><span class="sxs-lookup"><span data-stu-id="ac23a-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="ac23a-p103">實體集區只能與其他實體集區配對。同樣地，虛擬集區只能與其他虛擬集區配對。</span><span class="sxs-lookup"><span data-stu-id="ac23a-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="ac23a-113">一起配對的集區必須執行相同的作業系統。</span><span class="sxs-lookup"><span data-stu-id="ac23a-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="ac23a-114">拓撲產生器或拓撲驗證都不會禁止以非建議的方式來將兩個集區配對。</span><span class="sxs-lookup"><span data-stu-id="ac23a-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="ac23a-115">例如，拓撲產生器可讓您將 Enterprise Edition 集區與 Standard Edition 集區配對。</span><span class="sxs-lookup"><span data-stu-id="ac23a-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="ac23a-116">不過，不支援這些類型的配對。</span><span class="sxs-lookup"><span data-stu-id="ac23a-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="ac23a-117">配對中的每個集區都有在發生災害時，從這兩個集區服務所有使用者的能力。</span><span class="sxs-lookup"><span data-stu-id="ac23a-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="ac23a-118">如果您將 Enterprise Edition 集區配對，也可以在後端伺服器上實作高可用性，但若是 Standard Edition 集區配對，就只有災害復原措施可用。</span><span class="sxs-lookup"><span data-stu-id="ac23a-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

