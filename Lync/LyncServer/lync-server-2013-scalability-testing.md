---
title: Lync Server 2013 延展性測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be4dc8d08b9d8b1363af67af1a12aa56b59f0b9a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="61dcc-102">在 Lync Server 2013 中進行測試的延展性</span><span class="sxs-lookup"><span data-stu-id="61dcc-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61dcc-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="61dcc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="61dcc-104">Lync Server 2013 提供的伺服器基礎結構的所有 Lync Server 即時通訊，包括立即訊息 (IM) 和目前狀態、 會議以及 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="61dcc-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="61dcc-105">這包括任何功能會使用 Lync Server 2013 集區的硬體資源，並且因此，會影響效能和規模。</span><span class="sxs-lookup"><span data-stu-id="61dcc-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="61dcc-106">所有組織同樣也無法使用所有功能。</span><span class="sxs-lookup"><span data-stu-id="61dcc-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="61dcc-107">例如，某些組織可能使用視訊在會議中非常嚴重時其他人可能會很少或沒有視訊流量。</span><span class="sxs-lookup"><span data-stu-id="61dcc-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="61dcc-108">有些組織偏好共用應用程式共用，而其他人偏好相反的 PowerPoint 投影片。</span><span class="sxs-lookup"><span data-stu-id="61dcc-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="61dcc-109">部署 Enterprise Voice 這些組織可能或可能不常使用的回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="61dcc-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="61dcc-110">大多數的組織部署監控伺服器，但不是許多部署封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="61dcc-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="61dcc-111">此外，組織並非所有沒有相同的基礎結構，包括硬體容量、 網路容量及集區的數目和部署的集區的大小。</span><span class="sxs-lookup"><span data-stu-id="61dcc-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="61dcc-112">功能和基礎結構的多樣性帶來的挑戰延展性測試 – 不能以模擬的功能和基礎結構中的所有可能組合。</span><span class="sxs-lookup"><span data-stu-id="61dcc-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="61dcc-113">若要判斷延展性支援 Lync server，我們進行測試同時，使用 Lync Server 的所有功能的平均使用量模型 （使用者模型） 為基礎。</span><span class="sxs-lookup"><span data-stu-id="61dcc-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="61dcc-114">若要判斷適用於 Lync Server 工作負載的適當的使用者模型，我們分析多個資料點，包括客戶問卷調查、 來自 Microsoft 客戶經驗改進計畫的意見反應、 內部 IT 部門 microsoft Lync Server 使用狀況資料並從我們 Live Meeting 服務探索的資料。</span><span class="sxs-lookup"><span data-stu-id="61dcc-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="61dcc-115">在許多情況下，使用者模型有偏差向粗的負載，以針對組織內的使用狀況提供不感到安心邊界。</span><span class="sxs-lookup"><span data-stu-id="61dcc-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="61dcc-116">在我們的延展性測試，我們將設定 Lync Server 2013 集區，根據建議的硬體和軟體規格，包括基礎結構元件，例如 Active Directory 網域服務，硬體負載平衡器和防火牆。</span><span class="sxs-lookup"><span data-stu-id="61dcc-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="61dcc-117">我們將設定 Lync Server 環境盡可能將一般的真實環境。</span><span class="sxs-lookup"><span data-stu-id="61dcc-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="61dcc-118">我們接著會使用 [Lync Server 2013 壓力及效能工具來模擬 Lync Server 2013 負載 （以我們使用者模型為基礎）。</span><span class="sxs-lookup"><span data-stu-id="61dcc-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="61dcc-119">.</span><span class="sxs-lookup"><span data-stu-id="61dcc-119">.</span></span>

<span data-ttu-id="61dcc-120">我們執行動作延展性測試 （包括多個三週測試回合） 的多個反覆運算的次數。</span><span class="sxs-lookup"><span data-stu-id="61dcc-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="61dcc-121">協助符合效能調整以及驗證我們的使用者模型中的延展性數字的支援，我們會使用所有測試的結果。</span><span class="sxs-lookup"><span data-stu-id="61dcc-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

