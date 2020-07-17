---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="49e60-102">移轉 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="49e60-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e60-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="49e60-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="49e60-104">舊版 Office 通訊伺服器提供了可擴展的訊息和顯示狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署聯盟。</span><span class="sxs-lookup"><span data-stu-id="49e60-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="49e60-105">在 Lync Server 2013 中，可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="49e60-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="49e60-106">XMPP 功能是以兩個部分安裝：作為在 Lync Server 2013 Edge Server 上執行的 XMPP proxy，以及在 Lync Server 2013 前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="49e60-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="49e60-107">從遷移的角度來看，Office 通訊伺服器 2007 R2 使用者帳戶可以移至 Lync Server 2013 集區，並繼續使用 Office 通訊伺服器 2007 R2 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="49e60-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="49e60-108">只有在 Lync Server 2013 中未設定 XMPP 同盟合作者時，才可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="49e60-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="49e60-109">總而言之，如果 Office 通訊伺服器已與 Office 通訊伺服器 2007 R2 XMPP 閘道搭配使用，且已為舊版 Office 通訊伺服器 2007 R2 使用者啟用 XMPP 同盟，請將 XMPP 同盟遷移至 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="49e60-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="49e60-110">部署 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="49e60-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="49e60-111">部署 Lync Server 2013 Edge server。</span><span class="sxs-lookup"><span data-stu-id="49e60-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="49e60-112">將所有使用者移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="49e60-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="49e60-113">建立適用於 Edge Server 的 XMPP 存取原則及憑證。</span><span class="sxs-lookup"><span data-stu-id="49e60-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="49e60-114">在 Lync Server 2013 中啟用 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="49e60-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="49e60-115">更新 DNS 專案以指向 Lync Server 2013 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="49e60-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

