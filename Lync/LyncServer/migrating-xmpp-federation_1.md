---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761b0835eb8c1db84b8b969479ad329e7f75e033
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="c3869-102">移轉 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="c3869-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3869-103">_**主題上次修改日期：** 2012 年 10-16_</span><span class="sxs-lookup"><span data-stu-id="c3869-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c3869-104">舊版 Office Communications Server 提供可延伸訊息與顯示狀態通訊協定 (XMPP) 閘道，可以部署為不同的伺服器角色，以允許與 XMPP 部署同盟。</span><span class="sxs-lookup"><span data-stu-id="c3869-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="c3869-105">Lync Server 2013 中的 XMPP 功能可以部署為功能。</span><span class="sxs-lookup"><span data-stu-id="c3869-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="c3869-106">XMPP 功能安裝在兩個部分： 為 Lync Server 2013 Edge Server 執行 XMPP proxy 及 XMPP 閘道在 Lync Server 2013 前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c3869-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="c3869-107">移轉的觀點而言，Office Communications Server 2007 R2 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用 Office Communications Server 2007 R2 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c3869-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="c3869-108">只有當 Lync Server 2013 中沒有設定 XMPP 同盟協力廠商時，這是可能。</span><span class="sxs-lookup"><span data-stu-id="c3869-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="c3869-109">在 [摘要] 中，如果已部署 Office Communications Server 與 Office Communications Server 2007 R2 XMPP 閘道與舊版 Office Communications Server 2007 R2 使用者，將 XMPP 同盟移轉至 Lync Server 2013 已啟用 XMPP 同盟：</span><span class="sxs-lookup"><span data-stu-id="c3869-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="c3869-110">部署 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c3869-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="c3869-111">部署 Lync Server 2013 Edge server。</span><span class="sxs-lookup"><span data-stu-id="c3869-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="c3869-112">將所有使用者都移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c3869-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="c3869-113">建立適用於 Edge Server 的 XMPP 存取原則及憑證。</span><span class="sxs-lookup"><span data-stu-id="c3869-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="c3869-114">啟用 Lync Server 2013 中的 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="c3869-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="c3869-115">更新以指到 Lync Server 2013 XMPP 閘道的 DNS 項目。</span><span class="sxs-lookup"><span data-stu-id="c3869-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

