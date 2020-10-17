---
title: 必要條件
description: 先決條件。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560099"
---
# <a name="prerequisites"></a><span data-ttu-id="f9f6b-103">先決條件</span><span class="sxs-lookup"><span data-stu-id="f9f6b-103">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9f6b-104">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="f9f6b-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="f9f6b-105">您需要執行 Lync Server 2013 壓力和效能工具，各有不同的硬體、軟體和系統設定需求。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-105">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="f9f6b-106">用戶端硬體需求</span><span class="sxs-lookup"><span data-stu-id="f9f6b-106">Client Hardware Requirements</span></span>

<span data-ttu-id="f9f6b-107">若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力和效能工具，針對您想要模擬其負載的每一個4500使用者，您至少需要一部專用電腦，滿足下列基本硬體需求：</span><span class="sxs-lookup"><span data-stu-id="f9f6b-107">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="f9f6b-108">1 gb 網路介面卡</span><span class="sxs-lookup"><span data-stu-id="f9f6b-108">1 gigabit network adapter</span></span>

  - <span data-ttu-id="f9f6b-109">8 GB ram</span><span class="sxs-lookup"><span data-stu-id="f9f6b-109">8-GB ram</span></span>

  - <span data-ttu-id="f9f6b-110">2顆雙核中央處理單位 (CPUs) </span><span class="sxs-lookup"><span data-stu-id="f9f6b-110">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="f9f6b-111">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="f9f6b-111">Client Software Requirements</span></span>

<span data-ttu-id="f9f6b-112">若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力和效能工具，支援的作業系統包括：</span><span class="sxs-lookup"><span data-stu-id="f9f6b-112">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="f9f6b-113">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="f9f6b-113">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="f9f6b-114">Windows Server 2008 作業系統 (64-位版本) </span><span class="sxs-lookup"><span data-stu-id="f9f6b-114">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="f9f6b-115">您的用戶端電腦必須符合下列軟體需求：</span><span class="sxs-lookup"><span data-stu-id="f9f6b-115">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="f9f6b-116">您必須已安裝 [Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-116">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="f9f6b-117">在 Windows Server 2008/Windows Server 2012 上，必須啟用桌面體驗功能。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-117">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="f9f6b-118">您必須安裝 [Microsoft Visual c + + 2012 可轉散發元件套件](https://go.microsoft.com/fwlink/?linkid=143216) (x64) 。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-118">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="f9f6b-119">完全設定的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-119">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9f6b-120">Microsoft 整合通訊 Managed API (UCMA) 4.0 文件庫會包含在安裝套件中，因此不需要 UCMA，也不應該安裝在用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-120">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="f9f6b-121">設定需求</span><span class="sxs-lookup"><span data-stu-id="f9f6b-121">Configuration Requirements</span></span>

<span data-ttu-id="f9f6b-122">將執行 Lync Server 2013 壓力和效能工具的電腦必須依照下列需求進行設定：</span><span class="sxs-lookup"><span data-stu-id="f9f6b-122">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="f9f6b-123">您必須以 Domain 或 Local Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-123">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="f9f6b-124">Lync Server 2013 應力和效能工具 ( # A0) 無法在同時執行 Lync Server 2013 元件的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-124">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="f9f6b-125">您必須在前端伺服器或使用者帳戶所在的 Standard Edition 伺服器上，執行 [Lync Server 2013] 使用者建立工具 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-125">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="f9f6b-126">當該工具執行多次時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-126">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="f9f6b-127">頁面檔案大小應為系統管理，或至少應為系統上的 RAM 量的1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="f9f6b-127">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

