---
title: Lync Server 2013：部署 Lync 用戶端
description: Lync Server 2013：部署 Lync 用戶端。
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
ms.openlocfilehash: 09b501fc721ac880c5cf7da0293e3aa9c6443722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573429"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="e93dd-103">在 Lync Server 2013 中部署 Lync 用戶端</span><span class="sxs-lookup"><span data-stu-id="e93dd-103">Deploying Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93dd-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e93dd-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e93dd-105">Lync 2013 為用戶端部署引入了不同的方法。</span><span class="sxs-lookup"><span data-stu-id="e93dd-105">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="e93dd-106">在舊版本的出發中，Lync 2013 不再有自己的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="e93dd-106">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="e93dd-107">相反地，Lync 隨附于 Office 2013 安裝程式中。</span><span class="sxs-lookup"><span data-stu-id="e93dd-107">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="e93dd-108">若要將 Lync 2013 部署至使用者，您可以使用 Office 2013 安裝方法和自訂工具。</span><span class="sxs-lookup"><span data-stu-id="e93dd-108">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="e93dd-109">**Office 2013 Windows installer** 是以 Windows Installer 為基礎的安裝套件，由多個 MSI 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="e93dd-109">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="e93dd-110">中性語言核心 MSI 套件結合了一或多個特定語言套件，組成完整的產品。</span><span class="sxs-lookup"><span data-stu-id="e93dd-110">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="e93dd-111">安裝程式組合了個別套件，在安裝 Office 於使用者的電腦期間 (以及之後)，執行自訂與維護工作。</span><span class="sxs-lookup"><span data-stu-id="e93dd-111">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="e93dd-112">本節中的主題說明如何使用和自訂 Office 2013 Windows Installer 來部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="e93dd-112">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="e93dd-113">**Office 2013 Click-to-Run** 是一種安裝程式，可將 Office 安裝檔案從 Microsoft 365 系統管理中心流式傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="e93dd-113">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="e93dd-114">管理員可以使用隨選即用的 Office 部署工具來自訂安裝。</span><span class="sxs-lookup"><span data-stu-id="e93dd-114">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="e93dd-115">由於 Office 2013 Click-to-Run 主要用於 Microsoft 365 環境，因此本節中不會詳細說明此安裝方法。</span><span class="sxs-lookup"><span data-stu-id="e93dd-115">Because Office 2013 Click-to-Run is primarily used in the Microsoft 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="e93dd-116">Office 2013 資源套件檔中提供有關使用和自訂 Click-to-Run 安裝的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e93dd-116">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="e93dd-117">系統管理員也可以將 Office 2013 Click-to-Run 程式和語言來源檔案下載至內部部署位置，當您想要將網路需求降至最低，或由於公司的安全性需求而防止使用者從網際網路安裝軟體時，這是很有用的。</span><span class="sxs-lookup"><span data-stu-id="e93dd-117">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="e93dd-118">本節中的主題將著重說明如何使用 Office 2013 MSI 安裝程式部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="e93dd-118">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="e93dd-119">您的主要參考應該是 Office 2013 資源套件檔，其詳細說明如何準備基礎結構、自訂安裝及部署 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e93dd-119">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="e93dd-120">不過，您應該將 Office 檔與本節中的主題搭配使用，以指出 Lync 2013 特有的部署考慮。</span><span class="sxs-lookup"><span data-stu-id="e93dd-120">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="e93dd-121">Lync 2013 的線上會議增益集（支援來自 Outlook 郵件和共同作業用戶端的會議管理）會自動使用 Lync 2013 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="e93dd-121">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="e93dd-122">Office 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="e93dd-122">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="e93dd-123">Lync 2013 用戶端會與其他 Lync 或 Office Communicator 用戶端同時安裝</span><span class="sxs-lookup"><span data-stu-id="e93dd-123">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e93dd-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e93dd-124">In This Section</span></span>

  - [<span data-ttu-id="e93dd-125">在 Lync Server 2013 中自訂用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="e93dd-125">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="e93dd-126">在 Lync Server 2013 中自訂 Lync 行為和使用者介面</span><span class="sxs-lookup"><span data-stu-id="e93dd-126">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="e93dd-127">在 Lync Server 2013 中自訂線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="e93dd-127">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="e93dd-128">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="e93dd-128">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="e93dd-129">在 Lync Server 2013 中設定支援的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="e93dd-129">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="e93dd-130">在 Lync Server 2013 中設定增強型目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="e93dd-130">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

