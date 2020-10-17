---
title: Lync Server 2013： Lync Server 混合式環境的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99aeda6136c79b7ffda9b5cd3d5dced3b1f6ee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516110"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="40640-102">Lync Server 2013 混合式環境的概述</span><span class="sxs-lookup"><span data-stu-id="40640-102">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40640-103">_**主題上次修改日期：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="40640-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="40640-104">Lync Server 2013 混合式環境指的是內部部署的 Lync Server 2013 和其他使用者（位於 Lync Online 中）中有一些使用者，但使用者共用相同的網域，例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="40640-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="40640-105">關於本指南</span><span class="sxs-lookup"><span data-stu-id="40640-105">About this Guide</span></span>

<span data-ttu-id="40640-106">本指南說明設定 Lync Server 2013 環境與 Lync Online 互通性時所需的工作，然後將您的內部部署使用者移至使用 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="40640-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="40640-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="40640-107">Prerequisites</span></span>

<span data-ttu-id="40640-108">您必須安裝下列應用程式和公用程式，才可完成設定混合式部署的工作。</span><span class="sxs-lookup"><span data-stu-id="40640-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="40640-109">這些檔案的安裝程式會包含在您部署的安裝媒體上，以及下列清單中包含的連結。</span><span class="sxs-lookup"><span data-stu-id="40640-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="40640-110">Active Directory Federation Services (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="40640-110">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="40640-111">Microsoft 目錄同步作業工具9。1</span><span class="sxs-lookup"><span data-stu-id="40640-111">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="40640-112">安裝 Windows PowerShell 以進行單一登入與 AD FS</span><span class="sxs-lookup"><span data-stu-id="40640-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="40640-113">Microsoft Online Services 登入小幫手 ( # A0) 隨附于 Microsoft 365 的桌面安裝程式，可以從 Microsoft 365 系統管理中心連結的下載頁面取得。</span><span class="sxs-lookup"><span data-stu-id="40640-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="40640-114">系統管理員認證</span><span class="sxs-lookup"><span data-stu-id="40640-114">Administrator Credentials</span></span>

<span data-ttu-id="40640-115">當系統要求您提供系統管理員認證時，請使用 Microsoft 365 或 Office 365 組織之系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="40640-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="40640-116">當您設定 Active Directory Federation Services (AD FS) 2.0、目錄同步處理、單一登入、同盟，以及移動使用者至 Lync Online 時，也會使用這些認證。</span><span class="sxs-lookup"><span data-stu-id="40640-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="40640-117">連接至 Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="40640-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="40640-118">管理員現在具備使用 Windows PowerShell 管理 Lync Online 和其 Lync Online 使用者帳戶的能力。</span><span class="sxs-lookup"><span data-stu-id="40640-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="40640-119">若要這麼做，您必須先從 Microsoft 下載中心 (下載並安裝 Lync Online Connector 模組 https://go.microsoft.com/fwlink/?LinkId=294688) 。</span><span class="sxs-lookup"><span data-stu-id="40640-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="40640-120">如需下載、安裝和使用 Lync Online 連接器模組的詳細資訊，以及使用 Windows PowerShell 來管理 Lync Online 的詳細資訊，請參閱 [使用 windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="40640-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

