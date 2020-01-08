---
title: Lync Server 2013 支援的 [池配對] 選項和最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="f92f9-102">支援 Lync Server 2013 的池配對選項和最佳做法</span><span class="sxs-lookup"><span data-stu-id="f92f9-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f92f9-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="f92f9-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="f92f9-104">在兩個資料中心之間的距離沒有限制，包括彼此配對的前端池。</span><span class="sxs-lookup"><span data-stu-id="f92f9-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="f92f9-105">我們建議您在同一個世界區域使用兩個資料中心，並在它們之間進行高速連結。</span><span class="sxs-lookup"><span data-stu-id="f92f9-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="f92f9-106">最好的做法是將兩個資料中心分割得足夠，以避免單一災難同時發生。</span><span class="sxs-lookup"><span data-stu-id="f92f9-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="f92f9-107">您可以跨世界區域進行兩個資料中心，但由於資料複製中的延遲，可能會造成較高的資料遺失。</span><span class="sxs-lookup"><span data-stu-id="f92f9-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="f92f9-108">規劃要配對的池時，您必須記住，只有下列配對是受支援的：</span><span class="sxs-lookup"><span data-stu-id="f92f9-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="f92f9-109">企業版池只能與其他企業版池搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f92f9-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="f92f9-110">同樣地，標準版池只能與其他標準版池成對使用。</span><span class="sxs-lookup"><span data-stu-id="f92f9-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="f92f9-111">物理池只能與其他物理池進行配對。</span><span class="sxs-lookup"><span data-stu-id="f92f9-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="f92f9-112">同樣地，虛擬池只能與其他虛擬池成對。</span><span class="sxs-lookup"><span data-stu-id="f92f9-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="f92f9-113">成對組成的池必須執行相同的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f92f9-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="f92f9-114">拓撲產生器和拓撲驗證都不會以不遵循這些建議的方式來禁止配對兩個池。</span><span class="sxs-lookup"><span data-stu-id="f92f9-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="f92f9-115">例如，拓撲建立器可讓您將企業版池與標準版池配對。</span><span class="sxs-lookup"><span data-stu-id="f92f9-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="f92f9-116">不過，不支援這些類型的配對。</span><span class="sxs-lookup"><span data-stu-id="f92f9-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="f92f9-117">成對中的每個池，都應該有能力，以便在發生災難事件時，從兩個池的所有使用者都能提供服務。</span><span class="sxs-lookup"><span data-stu-id="f92f9-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="f92f9-118">如果您要將企業版池配對，您也可以在後端伺服器上執行高可用性，但適用于標準版池，只提供災害復原測量。</span><span class="sxs-lookup"><span data-stu-id="f92f9-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

