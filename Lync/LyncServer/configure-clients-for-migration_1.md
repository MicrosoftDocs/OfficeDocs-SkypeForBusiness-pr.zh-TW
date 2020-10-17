---
title: 設定用戶端以進行移轉
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a0b7bfead8f74e27d8539038cf768b1a85b72e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499560"
---
# <a name="configure-clients-for-migration"></a><span data-ttu-id="03dff-102">設定用戶端以進行移轉</span><span class="sxs-lookup"><span data-stu-id="03dff-102">Configure clients for migration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03dff-103">_**主題上次修改日期：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="03dff-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="03dff-104">本主題包含在遷移至 Lync Server 2013 之前，應採取的建議用戶端部署步驟。</span><span class="sxs-lookup"><span data-stu-id="03dff-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="03dff-105">您應該在 Office 通訊伺服器 2007 R2 上進行這些設定變更。</span><span class="sxs-lookup"><span data-stu-id="03dff-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="03dff-106">在遷移之前，請務必先執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="03dff-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="03dff-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃用戶端和裝置](lync-server-2013-planning-for-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="03dff-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="03dff-108">在遷移之前設定用戶端</span><span class="sxs-lookup"><span data-stu-id="03dff-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="03dff-109">在 (修復程式) 上部署最近的 Office 通訊伺服器 2007 R2 伺服器、用戶端及裝置更新：</span><span class="sxs-lookup"><span data-stu-id="03dff-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="03dff-110">套用 Office 通訊伺服器 2007 R2 更新</span><span class="sxs-lookup"><span data-stu-id="03dff-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="03dff-111">Communicator 2007 R2 累計更新套件的描述</span><span class="sxs-lookup"><span data-stu-id="03dff-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="03dff-112">取得裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="03dff-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="03dff-113">在 Office 通訊伺服器 2007 R2 上，使用用戶端版本篩選，只允許安裝了最新更新的 Office 通訊伺服器 2007 R2 用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="03dff-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="03dff-114">在 Office 通訊伺服器 2007 R2 上，使用用戶端版本篩選功能封鎖 Lync Server 2013 用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="03dff-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="03dff-115">依照設定 **用戶端版本篩選** 中所述的步驟 [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) ，新增下表所列的版本篩選器。</span><span class="sxs-lookup"><span data-stu-id="03dff-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="03dff-116">針對每個版本篩選，指派 action **區塊**。</span><span class="sxs-lookup"><span data-stu-id="03dff-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="03dff-117">用戶端</span><span class="sxs-lookup"><span data-stu-id="03dff-117">Client</span></span></th>
    <th><span data-ttu-id="03dff-118">使用者代理程式標頭</span><span class="sxs-lookup"><span data-stu-id="03dff-118">User agent header</span></span></th>
    <th><span data-ttu-id="03dff-119">版本</span><span class="sxs-lookup"><span data-stu-id="03dff-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="03dff-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03dff-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="03dff-121">Oc</span><span class="sxs-lookup"><span data-stu-id="03dff-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="03dff-122">15 ...\* \*\*</span><span class="sxs-lookup"><span data-stu-id="03dff-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="03dff-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="03dff-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="03dff-124">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="03dff-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="03dff-125">5 ...\* \*\*</span><span class="sxs-lookup"><span data-stu-id="03dff-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="03dff-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="03dff-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="03dff-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="03dff-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="03dff-128">4 ...\* \*\*</span><span class="sxs-lookup"><span data-stu-id="03dff-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

