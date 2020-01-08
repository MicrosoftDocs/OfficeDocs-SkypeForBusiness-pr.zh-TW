---
title: Lync Server 2013：Lync Server 混合式環境概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="d6245-102">Lync Server 2013 混合式環境概觀</span><span class="sxs-lookup"><span data-stu-id="d6245-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6245-103">_**主題上次修改日期：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="d6245-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="d6245-104">Lync Server 2013 混合式環境指的是在內部部署 Lync Server 2013 和其他使用者駐留在 Lync Online 的使用者，但使用者共用同一個網域，例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d6245-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="d6245-105">關於本指南</span><span class="sxs-lookup"><span data-stu-id="d6245-105">About this Guide</span></span>

<span data-ttu-id="d6245-106">本指南說明設定您的 Lync Server 2013 環境以進行 Lync Online 互通性所需執行的工作，然後從內部部署的部署將使用者移至使用 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="d6245-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="d6245-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="d6245-107">Prerequisites</span></span>

<span data-ttu-id="d6245-108">您必須安裝下列應用程式和實用程式，才能完成設定混合式部署的工作。</span><span class="sxs-lookup"><span data-stu-id="d6245-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="d6245-109">這些檔案的安裝程式會包含在您的部署所提供的安裝媒體，以及下列清單中的連結。</span><span class="sxs-lookup"><span data-stu-id="d6245-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="d6245-110">Active Directory 同盟服務（AD FS）2。0</span><span class="sxs-lookup"><span data-stu-id="d6245-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="d6245-111">Microsoft Directory 同步處理工具9。1</span><span class="sxs-lookup"><span data-stu-id="d6245-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="d6245-112">安裝 Windows PowerShell 以進行單一登入與 AD FS</span><span class="sxs-lookup"><span data-stu-id="d6245-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="d6245-113">Microsoft Online Services 登入小幫手（msoidcli-7.0）隨附于 Office 365 的桌面設定，可從 Office 365 系統管理入口網站連結至的下載頁面中取得。</span><span class="sxs-lookup"><span data-stu-id="d6245-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="d6245-114">系統管理員認證</span><span class="sxs-lookup"><span data-stu-id="d6245-114">Administrator Credentials</span></span>

<span data-ttu-id="d6245-115">當系統詢問您是否要提供您的系統管理員認證時，請針對您的 Office 365 租使用者使用系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="d6245-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="d6245-116">當您設定 Active Directory Federation Services （AD FS）2.0、目錄同步處理、單一登入、同盟，以及將使用者移至 Lync Online 時，您也會使用這些認證。</span><span class="sxs-lookup"><span data-stu-id="d6245-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="d6245-117">連線至 Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6245-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="d6245-118">系統管理員現在能夠使用 Windows PowerShell 來管理 Lync Online 及其 Lync Online 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d6245-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="d6245-119">若要這樣做，您必須先從 Microsoft 下載中心下載並安裝 Lync Online 連接器模組（http://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="d6245-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="d6245-120">如需有關下載、安裝及使用 Lync Online 連接器模組的詳細資訊，以及如何使用 Windows powershell 來管理 lync Online 的詳細資訊，請參閱[使用 Windows powershell 管理 lync](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)online。</span><span class="sxs-lookup"><span data-stu-id="d6245-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

