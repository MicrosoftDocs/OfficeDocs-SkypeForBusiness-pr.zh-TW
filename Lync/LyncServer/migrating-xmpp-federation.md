---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="44289-102">移轉 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="44289-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44289-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="44289-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="44289-104">舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="44289-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="44289-105">在 Lync Server 2013 中，您可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="44289-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="44289-106">XMPP 功能已安裝于兩個部分：作為在 Lync Server 2013 Edge 伺服器上執行的 XMPP proxy，以及在 Lync Server 2013 前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="44289-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="44289-107">從遷移的角度來看，Lync Server 使用者帳戶可以移至 Lync Server 2013 池中，並繼續使用舊版 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="44289-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="44289-108">只有在 Lync Server 2013 沒有設定 XMPP 聯盟夥伴時，才能這麼做。</span><span class="sxs-lookup"><span data-stu-id="44289-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="44289-109">總之，如果已使用 Office 通訊伺服器 2007 R2 XMPP 閘道部署 Lync Server 2010，且已為舊版 Lync Server 2010 使用者啟用 XMPP 聯盟，請將 XMPP 同盟遷移至 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="44289-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="44289-110">部署 Lync Server 2013 文件庫。</span><span class="sxs-lookup"><span data-stu-id="44289-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="44289-111">部署 Lync Server 2013 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44289-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="44289-112">將所有使用者移至 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="44289-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="44289-113">建立邊緣伺服器的 XMPP 存取原則和憑證。</span><span class="sxs-lookup"><span data-stu-id="44289-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="44289-114">在 Lync Server 2013 中啟用 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="44289-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="44289-115">更新 DNS 專案以指向 Lync Server 2013 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="44289-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

