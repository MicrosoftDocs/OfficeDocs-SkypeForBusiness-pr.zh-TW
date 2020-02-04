---
title: Lync Server 2013：Windows PowerShell 和 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="43c3f-102">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="43c3f-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43c3f-103">_**主題上次修改日期：** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="43c3f-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="43c3f-104">在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 來實現。</span><span class="sxs-lookup"><span data-stu-id="43c3f-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="43c3f-105">Windows PowerShell 包含命令列環境、產品特定命令及完整的腳本撰寫語言。</span><span class="sxs-lookup"><span data-stu-id="43c3f-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="43c3f-106">使用 Windows PowerShell 實現的 Lync Server 2013 工具組括下列各項：</span><span class="sxs-lookup"><span data-stu-id="43c3f-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="43c3f-107">**拓撲**建立器。</span><span class="sxs-lookup"><span data-stu-id="43c3f-107">**Topology Builder**.</span></span> <span data-ttu-id="43c3f-108">您可以使用 [拓撲建立器] 來建立、調整及發佈規劃的拓撲，並在開始伺服器安裝之前驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="43c3f-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="43c3f-109">當您在個別伺服器上安裝 Lync Server 2013 時，伺服器會讀取已發佈的拓撲，做為安裝程式的一部分，而安裝程式會以拓撲中的指示方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="43c3f-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="43c3f-110">安裝完成後，系統會自動將配置資訊複製到所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="43c3f-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="43c3f-111">只有使用拓撲建立器，才能將元件新增至您的部署。</span><span class="sxs-lookup"><span data-stu-id="43c3f-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="43c3f-112">**Lync Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="43c3f-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="43c3f-113">您可以使用 Lync Server 管理命令介面進行部署的完整命令列管理。</span><span class="sxs-lookup"><span data-stu-id="43c3f-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="43c3f-114">**Lync Server [控制台**]。</span><span class="sxs-lookup"><span data-stu-id="43c3f-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="43c3f-115">您可以使用 Microsoft Lync Server 2013 的 [控制台] 使用者介面來管理部署中最常見的工作。</span><span class="sxs-lookup"><span data-stu-id="43c3f-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="43c3f-116">這些工具使用 Windows PowerShell Cmdlet 來管理您的部署，包括關閉至550產品專用的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="43c3f-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="43c3f-117">Lync Server 2013 中包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="43c3f-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="43c3f-118">有多種不同的 Cmdlet 可用於管理驗證，包括憑證和個人識別碼（PIN）驗證的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="43c3f-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="43c3f-119">此外，有許多 Cmdlet 可讓您使用新的角色存取控制（RBAC）功能來委派 Lync Server 2013 的管理控制權。</span><span class="sxs-lookup"><span data-stu-id="43c3f-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="43c3f-120">如需 Lync Server Cmdlet 的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="43c3f-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="43c3f-121">Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術的一些腳本相關安全性問題，包括 Microsoft Visual Basic 腳本版本（VBScript）。</span><span class="sxs-lookup"><span data-stu-id="43c3f-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="43c3f-122">Windows PowerShell 安全性功能是用來建立使用者無法輕易或無意中執行腳本的環境。</span><span class="sxs-lookup"><span data-stu-id="43c3f-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="43c3f-123">根據預設，會啟用 Windows PowerShell 安全性功能。</span><span class="sxs-lookup"><span data-stu-id="43c3f-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="43c3f-124">您可以修改這些功能的狀態，以適應您的腳本需求，以及各種安全目標。</span><span class="sxs-lookup"><span data-stu-id="43c3f-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="43c3f-125">這不是說 shell 無法讓使用者執行腳本。</span><span class="sxs-lookup"><span data-stu-id="43c3f-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="43c3f-126">相反地，shell 會讓使用者在執行腳本時不會有任何困難（預設），而不會意識到這麼做。</span><span class="sxs-lookup"><span data-stu-id="43c3f-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="43c3f-127">如需詳細資訊，請參閱 Windows PowerShell [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)腳本安全性。</span><span class="sxs-lookup"><span data-stu-id="43c3f-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

