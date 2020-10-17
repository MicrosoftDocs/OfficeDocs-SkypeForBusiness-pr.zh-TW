---
title: Lync Server 2013：確認拓撲設計
description: Lync Server 2013：確認拓撲設計。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560189"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="d9edd-103">驗證 Lync Server 2013 中的拓撲設計</span><span class="sxs-lookup"><span data-stu-id="d9edd-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9edd-104">_**主題上次修改日期：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="d9edd-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="d9edd-105">拓撲產生器會自動驗證拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9edd-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="d9edd-106">任何拓撲錯誤都會識別為驗證錯誤，由伺服器角色旁邊的驗證錯誤圖示所指示。</span><span class="sxs-lookup"><span data-stu-id="d9edd-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="d9edd-107">此外，驗證此拓撲是否正確表示您的部署拓撲也很重要。</span><span class="sxs-lookup"><span data-stu-id="d9edd-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="d9edd-108">若要在發行之前驗證拓撲</span><span class="sxs-lookup"><span data-stu-id="d9edd-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="d9edd-109">檢查所有簡單 URL 皆已設定正確。</span><span class="sxs-lookup"><span data-stu-id="d9edd-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="d9edd-110">確認以 SQL Server 為基礎的伺服器在線上，且可供安裝拓撲產生器的電腦使用（包括任何必要的防火牆規則）。</span><span class="sxs-lookup"><span data-stu-id="d9edd-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="d9edd-111">確認檔案共用可用且具有適當的許可權定義。</span><span class="sxs-lookup"><span data-stu-id="d9edd-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="d9edd-112">確認拓撲中已定義符合部署需求的正確伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="d9edd-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="d9edd-113">確認伺服器存在於 Active Directory 網域服務中。</span><span class="sxs-lookup"><span data-stu-id="d9edd-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="d9edd-114">如果您已將伺服器加入至網域，則會自動發生這種情形。</span><span class="sxs-lookup"><span data-stu-id="d9edd-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="d9edd-115">當您已驗證拓撲且沒有驗證錯誤時，您應可準備發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9edd-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="d9edd-116">如果有驗證錯誤，您必須先更正錯誤，才可以發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d9edd-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="d9edd-117">如需有關發佈拓撲的詳細資訊，請參閱 [在 Lync Server 2013 中發行拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="d9edd-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

