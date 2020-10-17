---
title: 'Lync Server 2013：使用 Office 自訂工具 (OCT) '
description: Lync Server 2013：使用 Office 自訂工具 (OCT) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547329"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="a4fd4-103">在 Lync Server 2013 中使用 Office 自訂工具 (OCT) </span><span class="sxs-lookup"><span data-stu-id="a4fd4-103">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4fd4-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a4fd4-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a4fd4-105">Office 自訂工具 (OCT) 屬於安裝程式的一部分，也是許多自訂的建議使用工具。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="a4fd4-106">您可以使用 OCT 自訂 Office，並將自訂儲存在安裝程式自訂 .msp 檔案中。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="a4fd4-107">您將此檔案放在網路安裝點上的 Updates 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="a4fd4-108">當您安裝 Office 時，安裝程式會在 Updates 資料夾中尋找安裝程式自訂檔案，並套用自訂。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="a4fd4-109">「更新」資料夾僅可用於在 Office 2013 的初始安裝期間部署軟體更新。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-109">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="a4fd4-110">OCT 是安裝程式的一部分，且包含在產品的大量授權版本中。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-110">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="a4fd4-111">您可以 `setup.exe /admin` 從包含 Office 2013 來源檔案之網路安裝點的根目錄輸入命令列，以執行 OCT。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-111">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="a4fd4-112">例如，使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="a4fd4-112">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="a4fd4-113">管理員使用 OCT 建立安裝程式自訂 .msp 檔案。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-113">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="a4fd4-114">如 Microsoft Office 2010 OCT 中所示，管理員可以自訂下欄區域：</span><span class="sxs-lookup"><span data-stu-id="a4fd4-114">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="a4fd4-115">**安裝程式** 用於指定用戶端的預設安裝位置和預設組織名稱、其他網路安裝來源、產品金鑰、使用者授權合約、顯示層級、要移除的舊版 Office、要在安裝期間執行的自訂程式、安全性設定，以及安裝程式屬性。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-115">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="a4fd4-116">**功能** 用來設定使用者設定，以及自訂安裝 Office 功能的方式。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-116">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="a4fd4-117">系統管理員可以使用 OCT 為使用者指定 Office 應用程式設定的初始預設值。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-117">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="a4fd4-118">使用者可以在安裝之後修改大部分的設定。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-118">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="a4fd4-119">**其他內容** 用於新增或移除檔案、新增或移除登錄專案，以及設定快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-119">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="a4fd4-120">**Outlook** 用來自訂使用者的預設 Outlook 設定檔、指定 Exchange 設定、新增帳戶、移除帳戶和匯出設定，以及指定傳送 \\ 接收群組。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-120">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="a4fd4-121">如需 OCT 的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="a4fd4-121">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

