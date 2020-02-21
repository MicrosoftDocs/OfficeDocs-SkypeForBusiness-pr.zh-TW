---
title: 必要條件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4f10cb1bdf5733dbe54519325475871be10564
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="949b5-102">必要條件</span><span class="sxs-lookup"><span data-stu-id="949b5-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="949b5-103">_**上次修改主題：** 2013年-02-19_</span><span class="sxs-lookup"><span data-stu-id="949b5-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="949b5-104">有各種硬體、 軟體和系統組態需求，您必須先執行 Lync Server 2013 壓力及效能工具。</span><span class="sxs-lookup"><span data-stu-id="949b5-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="949b5-105">用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="949b5-105">Client Hardware Requirements</span></span>

<span data-ttu-id="949b5-106">若要執行 Lync Server 2013 部署，為每個 4500 使用者想要模擬，其負載上的 [Lync Server 2013 壓力及效能工具，您必須至少一個專用的電腦符合下列基本硬體需求：</span><span class="sxs-lookup"><span data-stu-id="949b5-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="949b5-107">1gb 網路介面卡</span><span class="sxs-lookup"><span data-stu-id="949b5-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="949b5-108">8 GB ram</span><span class="sxs-lookup"><span data-stu-id="949b5-108">8-GB ram</span></span>

  - <span data-ttu-id="949b5-109">2 顆雙核心管理中心處理單位 (Cpu)</span><span class="sxs-lookup"><span data-stu-id="949b5-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="949b5-110">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="949b5-110">Client Software Requirements</span></span>

<span data-ttu-id="949b5-111">若要在 Lync Server 2013 部署上執行 [Lync Server 2013 壓力及效能工具，是支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="949b5-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="949b5-112">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="949b5-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="949b5-113">Windows Server 2008 作業系統 （64 位元版本）</span><span class="sxs-lookup"><span data-stu-id="949b5-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="949b5-114">在用戶端電腦必須符合下列軟體需求：</span><span class="sxs-lookup"><span data-stu-id="949b5-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="949b5-115">您必須安裝[Microsoft.NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)執行階段。</span><span class="sxs-lookup"><span data-stu-id="949b5-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="949b5-116">在 Windows Server 2008/Windows Server 2012 上必須啟用桌面體驗功能。</span><span class="sxs-lookup"><span data-stu-id="949b5-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="949b5-117">您必須擁有[Microsoft Visual c + + 2012年可轉散發套件](https://go.microsoft.com/fwlink/?linkid=143216)(x64) 安裝。</span><span class="sxs-lookup"><span data-stu-id="949b5-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="949b5-118">完整設定的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="949b5-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="949b5-119">Microsoft Unified Communications Managed API (UCMA) 4.0 文件庫中隨附的安裝套件，讓 UCMA 則不需要，因此不應安裝用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="949b5-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="949b5-120">設定需求</span><span class="sxs-lookup"><span data-stu-id="949b5-120">Configuration Requirements</span></span>

<span data-ttu-id="949b5-121">會執行 Lync Server 2013 壓力及效能工具的電腦必須被設定是根據下列需求：</span><span class="sxs-lookup"><span data-stu-id="949b5-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="949b5-122">您必須網域或本機系統管理員群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="949b5-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="949b5-123">無法執行 Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe)，也執行 Lync Server 2013 元件的電腦上。</span><span class="sxs-lookup"><span data-stu-id="949b5-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="949b5-124">您必須執行 Lync Server 2013 使用者建立工具 (UserProvisioningTool.exe)，Standard Edition server 或前端伺服器上的使用者帳戶所在的位置。</span><span class="sxs-lookup"><span data-stu-id="949b5-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="949b5-125">當多次時，會執行此工具時，Microsoft 整合通訊啟用每個使用者必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="949b5-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="949b5-126">分頁檔案大小應系統管理，或應該至少 1.5 倍 RAM 的數量系統上。</span><span class="sxs-lookup"><span data-stu-id="949b5-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

