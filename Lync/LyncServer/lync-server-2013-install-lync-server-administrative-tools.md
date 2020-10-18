---
title: Lync Server 2013：安裝 Lync Server 系統管理工具
description: Lync Server 2013：安裝 Lync Server 系統管理工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1ad96299197c3339d06c4f094784edc632e6b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574169"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="76791-103">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="76791-103">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76791-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="76791-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="76791-105">本主題說明如何安裝您需要用來部署和管理 Lync Server 2013 的系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="76791-105">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="76791-106">預設會在每一部執行 Lync Server 2013 的伺服器上安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="76791-106">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="76791-107">此外，您也可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="76791-107">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="76791-108">強烈建議您在所建立的 Lync Server 2013 部署所在的電腦上安裝系統管理工具，因為這樣做可以確定 Active Directory 網域服務準備步驟已完成，讓您稍後可以在該電腦上使用系統管理工具發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="76791-108">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="76791-109">在您安裝或使用 Lync Server 2013 系統管理工具之前，請務必先查看基礎結構、作業系統、軟體及系統管理員的許可權需求。</span><span class="sxs-lookup"><span data-stu-id="76791-109">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="76791-110">如需基礎結構需求的詳細資訊，請參閱 [Lync Server 2013 中的系統管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76791-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="76791-111">如需作業系統和軟體需求的詳細資訊，以安裝 Lync Server 2013 系統管理工具，請參閱 lync server [2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及 [Lync server 2013 中的其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76791-111">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="76791-112">如需安裝及使用工具所需之使用者權利的詳細資訊，請參閱 [設定和管理 Lync Server 2013 所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。</span><span class="sxs-lookup"><span data-stu-id="76791-112">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="76791-113">如果您的組織需要在系統磁片磁碟機以外的其他磁碟機上找到網際網路資訊服務 (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="76791-113">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="76791-114">若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會同時部署至此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="76791-114">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="76791-115">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="76791-115">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="76791-116">以本機系統管理員身分登入，將 (最低需求) 至您要安裝系統管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="76791-116">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="76791-117">如果您是以 Windows Vista 或 Windows 7 作業系統的標準使用者身分登入，而且使用者帳戶控制權 (UAC) 皆已啟用，系統會提示您輸入本機系統管理員或網域對等的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="76791-117">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="76791-118">找出電腦上的安裝媒體，然後按兩下 [ \\ Setup \\ amd64Setup.exe] \\ 。</span><span class="sxs-lookup"><span data-stu-id="76791-118">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="76791-119">如果系統提示您安裝 Microsoft Visual C++ 2008 可散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="76791-119">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="76791-120">在 [ **Microsoft Lync Server 2013 安裝位置** ] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="76791-120">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="76791-121">如果您需要將檔案安裝至其他位置，請將此路徑變更為其他位置或磁碟機。</span><span class="sxs-lookup"><span data-stu-id="76791-121">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="76791-122">如果您的組織需要在系統磁片磁碟機以外的其他磁碟機上找到網際網路資訊服務 (IIS) 和所有 Web 服務，您可以在 [安裝程式] 對話方塊中變更 Lync Server 2013 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="76791-122">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="76791-123">若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會部署至此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="76791-123">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="76791-p107">在 **[使用者授權合約]** 頁面上檢閱授權條款，然後依序按一下 **[我接受]** 和 **[確定]**。需要完成此步驟才能繼續。</span><span class="sxs-lookup"><span data-stu-id="76791-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="76791-126">在 [ **Microsoft Lync Server 2013 –部署嚮導]** 頁面上，按一下 [ **安裝系統管理員工具**]。</span><span class="sxs-lookup"><span data-stu-id="76791-126">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="76791-127">當安裝順利完成時，按一下 **[結束]**。</span><span class="sxs-lookup"><span data-stu-id="76791-127">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76791-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="76791-128">See Also</span></span>


[<span data-ttu-id="76791-129">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="76791-129">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="76791-130">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="76791-130">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

