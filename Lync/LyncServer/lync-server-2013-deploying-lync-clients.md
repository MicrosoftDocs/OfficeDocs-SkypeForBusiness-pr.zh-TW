---
title: Lync Server 2013： 部署 Lync 用戶端
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
ms.openlocfilehash: 0004e3ce0b3e00cb90fc93cee148844ebc5d4d7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="0e8b3-102">部署 Lync Server 2013 中的 Lync 用戶端</span><span class="sxs-lookup"><span data-stu-id="0e8b3-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8b3-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="0e8b3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0e8b3-104">Lync 2013 引進了用戶端部署的不同方法。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="0e8b3-105">從舊版不同，在 Lync 2013 就不再有它自己的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="0e8b3-106">相反地，Lync 隨附於 Office 2013 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="0e8b3-107">若要將 Lync 2013 部署到您的使用者，您可以使用 Office 2013 的安裝方式與自訂工具。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="0e8b3-108">**Office 2013 Windows Installer**是 Windows installer 安裝套件，包含多個 MSI 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="0e8b3-109">中性語言核心 MSI 套件結合了一或多個特定語言套件，組成完整的產品。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="0e8b3-110">安裝程式組合了個別套件，在安裝 Office 於使用者的電腦期間 (以及之後)，執行自訂與維護工作。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="0e8b3-111">本節中的主題說明如何使用和自訂 Office 2013 Windows 安裝程式，以部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="0e8b3-112">**Office 2013 隨-即**是會從 Microsoft Office 365 入口網站串流 Office 安裝程式檔案傳送給使用者的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="0e8b3-113">管理員可以使用隨選即用的 Office 部署工具來自訂安裝。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="0e8b3-114">由於 Office 2013 到隨主要用於 Microsoft Office 365 環境，本節中的詳細資料不說明此安裝方法。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="0e8b3-115">使用 Office 2013 Resource Kit > 文件中使用和自訂按一下-隨選即用安裝的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="0e8b3-116">系統管理員也可以下載至內部部署位置，也就是很有用，當您想要減少網路上的需求，或防止使用者從網際網路由於安裝軟體的 Office 2013 按一下-隨選即用程式及語言來源檔案公司安全性需求。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="0e8b3-117">本節中的主題著重於如何使用 Office 2013 MSI 型安裝程式來部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="0e8b3-118">您的主要參考應詳細說明如何準備您的基礎結構、 自訂安裝程式，並部署 Office 2013 Office 2013 Resource Kit > 文件。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="0e8b3-119">不過，您應該使用本節各主題中，這是專屬於 Lync 2013 的部署考量註明搭配 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="0e8b3-120">線上會議增益集 for Lync 2013 支援 Outlook 訊息和共同作業用戶端內管理會議，與 Lync 2013 自動安裝。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="0e8b3-121">Office 2013 安裝程式不會解除安裝舊版的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="0e8b3-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="0e8b3-122">Lync 2013 用戶端安裝並排顯示與其他 Lync 或 Office Communicator 用戶端</span><span class="sxs-lookup"><span data-stu-id="0e8b3-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e8b3-123">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0e8b3-123">In This Section</span></span>

  - [<span data-ttu-id="0e8b3-124">自訂 Lync Server 2013 中的用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="0e8b3-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="0e8b3-125">自訂 Lync 2010 和 Lync Server 2013 中的使用者介面</span><span class="sxs-lookup"><span data-stu-id="0e8b3-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="0e8b3-126">自訂的線上會議增益集在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8b3-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="0e8b3-127">Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="0e8b3-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="0e8b3-128">在 Lync Server 2013 中設定支援的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="0e8b3-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="0e8b3-129">在 Lync Server 2013 中設定增強的目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="0e8b3-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

