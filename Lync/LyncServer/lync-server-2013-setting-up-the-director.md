---
title: Lync Server 2013： 設定 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 676853eca95534d6167d4786c7bad2df00dff9de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="59d75-102">設定 Lync Server 2013 中 Director</span><span class="sxs-lookup"><span data-stu-id="59d75-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d75-103">_**上次修改主題：** 2014年-05-05_</span><span class="sxs-lookup"><span data-stu-id="59d75-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="59d75-104">如果您正在部署 Edge Server 啟用外部使用者的存取，其中一個選項是部署 Director。</span><span class="sxs-lookup"><span data-stu-id="59d75-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="59d75-105">Director 是執行 Microsoft Lync Server 2013 的驗證使用者要求，但不會首頁的任何使用者帳戶的伺服器。</span><span class="sxs-lookup"><span data-stu-id="59d75-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="59d75-106">現在，這不是必要項，但是如果您擔心效能，並且想要協助簡化驗證要求，它是很有幫助。</span><span class="sxs-lookup"><span data-stu-id="59d75-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="59d75-107">如果您決定這是您的組織很好的作法，Director 或 Director 集區設定的步驟會類似於設定 Enterprise Edition 前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="59d75-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="59d75-108">您已定義您的 director 拓撲產生器中之後，您需要執行本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="59d75-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59d75-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="59d75-109">In This Section</span></span>

  - [<span data-ttu-id="59d75-110">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="59d75-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="59d75-111">在 Director 上安裝 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59d75-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="59d75-112">Lync Server 2013 中 director 設定憑證</span><span class="sxs-lookup"><span data-stu-id="59d75-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="59d75-113">Lync Server 2013 中在 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="59d75-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="59d75-114">在 Lync Server 2013 中測試 Director</span><span class="sxs-lookup"><span data-stu-id="59d75-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="59d75-115">設定自動用戶端登入 Lync Server 2013 中使用 Director</span><span class="sxs-lookup"><span data-stu-id="59d75-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

