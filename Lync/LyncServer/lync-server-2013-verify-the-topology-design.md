---
title: Lync Server 2013：驗證拓撲設計
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
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="0157d-102">在 Lync Server 2013 中驗證拓撲設計</span><span class="sxs-lookup"><span data-stu-id="0157d-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0157d-103">_**主題上次修改日期：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="0157d-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="0157d-104">[拓撲建立器] 會自動驗證拓撲。</span><span class="sxs-lookup"><span data-stu-id="0157d-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="0157d-105">任何拓撲錯誤都會被識別為驗證錯誤，並由伺服器角色旁的驗證錯誤圖示所指示。</span><span class="sxs-lookup"><span data-stu-id="0157d-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="0157d-106">您也必須確認拓撲正確代表您部署的拓撲。</span><span class="sxs-lookup"><span data-stu-id="0157d-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="0157d-107">在發佈前驗證拓撲</span><span class="sxs-lookup"><span data-stu-id="0157d-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="0157d-108">檢查所有簡單的 Url 是否已正確設定。</span><span class="sxs-lookup"><span data-stu-id="0157d-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="0157d-109">確認 SQL Server 型伺服器已在線上且可供安裝拓撲產生器的電腦使用，包括任何必要的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="0157d-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="0157d-110">確認檔案共用可用，且已定義適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="0157d-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="0157d-111">確認拓撲中定義符合部署需求的正確伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0157d-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="0157d-112">確認伺服器存在於 Active Directory 網域服務中。</span><span class="sxs-lookup"><span data-stu-id="0157d-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="0157d-113">如果您已將伺服器加入網域，就會自動進行這種情況。</span><span class="sxs-lookup"><span data-stu-id="0157d-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="0157d-114">驗證拓朴且沒有驗證錯誤時，您應該準備好發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="0157d-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="0157d-115">如果有驗證錯誤，您必須先更正這些錯誤，才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="0157d-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="0157d-116">如需發佈拓撲的詳細資料，請參閱[在 Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="0157d-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

