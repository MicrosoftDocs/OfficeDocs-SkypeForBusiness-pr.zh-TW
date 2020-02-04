---
title: Lync Server 2013：部署 Lync 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="744ed-102">在 Lync Server 2013 中部署 Lync 用戶端</span><span class="sxs-lookup"><span data-stu-id="744ed-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="744ed-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="744ed-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="744ed-104">Lync 2013 為用戶端部署帶來了不同的方法。</span><span class="sxs-lookup"><span data-stu-id="744ed-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="744ed-105">從先前的版本出發，Lync 2013 不再有自己的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="744ed-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="744ed-106">相反地，Lync 隨附于 Office 2013 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="744ed-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="744ed-107">若要將 Lync 2013 部署至您的使用者，您可以使用 Office 2013 安裝方法和自訂工具。</span><span class="sxs-lookup"><span data-stu-id="744ed-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="744ed-108">**Office 2013 Windows 安裝程式**是一個以 Windows 安裝程式為基礎的安裝套件，由多個 MSI 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="744ed-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="744ed-109">語言中立的核心 MSI 套件與一或多個語言特定套件結合，以製作完整的產品。</span><span class="sxs-lookup"><span data-stu-id="744ed-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="744ed-110">安裝程式會彙編個別套件，並在安裝使用者電腦上的 Office 期間和之後執行自訂及維護作業。</span><span class="sxs-lookup"><span data-stu-id="744ed-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="744ed-111">本節中的主題說明如何使用及自訂 Office 2013 Windows 安裝程式來部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="744ed-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="744ed-112">**Office 2013** [隨選即用] 是從 Microsoft office 365 入口網站將 Office 設定檔案流向使用者的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="744ed-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="744ed-113">系統管理員可以使用 Office 部署工具進行「隨選即用」來自訂安裝。</span><span class="sxs-lookup"><span data-stu-id="744ed-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="744ed-114">因為 Office 2013 隨選即用主要是在 Microsoft Office 365 環境中使用，所以本節不詳細說明此安裝方法。</span><span class="sxs-lookup"><span data-stu-id="744ed-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="744ed-115">有關使用及自訂「隨選即用」安裝的詳細資訊，請參閱 Office 2013 資源套件檔。</span><span class="sxs-lookup"><span data-stu-id="744ed-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="744ed-116">系統管理員也可以將 Office 2013 隨選即用程式及語言來源檔案下載到內部部署位置，這在您想要將網路上的需求最小化或防止使用者從網際網路安裝軟體時很有用。公司安全性需求。</span><span class="sxs-lookup"><span data-stu-id="744ed-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="744ed-117">本節中的主題將重點放在如何使用 Office 2013 MSI 安裝程式部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="744ed-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="744ed-118">您的主要參考應該是 Office 2013 資源套件檔，其中詳細說明如何準備您的基礎結構、自訂安裝程式，以及部署 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="744ed-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="744ed-119">不過，您應該將 Office 檔與本節中的主題搭配使用，以指出 Lync 2013 專用的部署考慮。</span><span class="sxs-lookup"><span data-stu-id="744ed-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="744ed-120">Lync 2013 的線上會議增益集（支援 Outlook 訊息和共同作業用戶端中的會議管理）會自動使用 Lync 2013 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="744ed-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="744ed-121">Office 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="744ed-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="744ed-122">Lync 2013 用戶端與其他 Lync 或 Office Communicator 用戶端並排安裝</span><span class="sxs-lookup"><span data-stu-id="744ed-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="744ed-123">本節內容</span><span class="sxs-lookup"><span data-stu-id="744ed-123">In This Section</span></span>

  - [<span data-ttu-id="744ed-124">在 Lync Server 2013 中自訂用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="744ed-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="744ed-125">在 Lync Server 2013 中自訂 Lync 行為和使用者介面</span><span class="sxs-lookup"><span data-stu-id="744ed-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="744ed-126">在 Lync Server 2013 中自訂線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="744ed-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="744ed-127">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="744ed-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="744ed-128">在 Lync Server 2013 中設定支援的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="744ed-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="744ed-129">在 Lync Server 2013 中設定增強的目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="744ed-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

