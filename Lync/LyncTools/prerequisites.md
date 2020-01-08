---
title: 先決條件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74603ed20fe144ca89d3ac13bc00fef0e7d6ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="3d975-102">先決條件</span><span class="sxs-lookup"><span data-stu-id="3d975-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d975-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="3d975-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="3d975-104">您必須執行 Lync Server 2013 應力和效能工具，才能執行各種硬體、軟體及系統設定需求。</span><span class="sxs-lookup"><span data-stu-id="3d975-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="3d975-105">用戶端硬體需求</span><span class="sxs-lookup"><span data-stu-id="3d975-105">Client Hardware Requirements</span></span>

<span data-ttu-id="3d975-106">若要在 Lync Server 2013 部署上執行 Lync Server 2013 應力和效能工具，請針對您想要模擬其負載的每個4500使用者，至少需要一個符合下列最低硬體需求的專用電腦：</span><span class="sxs-lookup"><span data-stu-id="3d975-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="3d975-107">1個十億位元網路介面卡</span><span class="sxs-lookup"><span data-stu-id="3d975-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="3d975-108">8 GB 的 ram</span><span class="sxs-lookup"><span data-stu-id="3d975-108">8-GB ram</span></span>

  - <span data-ttu-id="3d975-109">2個雙核中央處理單元（Cpu）</span><span class="sxs-lookup"><span data-stu-id="3d975-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="3d975-110">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="3d975-110">Client Software Requirements</span></span>

<span data-ttu-id="3d975-111">若要在 Lync Server 2013 部署上執行 Lync Server 2013 壓力與效能工具，支援的作業系統如下：</span><span class="sxs-lookup"><span data-stu-id="3d975-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="3d975-112">Windows Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="3d975-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="3d975-113">Windows Server 2008 作業系統（64位版本）</span><span class="sxs-lookup"><span data-stu-id="3d975-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="3d975-114">您的用戶端電腦必須符合下列軟體需求：</span><span class="sxs-lookup"><span data-stu-id="3d975-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="3d975-115">您必須已安裝[Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212)執行時間。</span><span class="sxs-lookup"><span data-stu-id="3d975-115">You must have the [Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="3d975-116">在 Windows Server 2008/Windows Server 2012 上，必須啟用 [桌面體驗] 功能。</span><span class="sxs-lookup"><span data-stu-id="3d975-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="3d975-117">您必須已安裝[Microsoft Visual c + + 2012 可再發行套件](http://go.microsoft.com/fwlink/?linkid=143216)（x64）。</span><span class="sxs-lookup"><span data-stu-id="3d975-117">You must have the [Microsoft Visual C++ 2012 redistributable package](http://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="3d975-118">完全設定的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="3d975-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d975-119">Microsoft 整合通訊管理 API （UCMA）4.0 文件庫包含在安裝套件中，因此不需要 UCMA，也不應該在用戶端電腦上安裝。</span><span class="sxs-lookup"><span data-stu-id="3d975-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="3d975-120">配置需求</span><span class="sxs-lookup"><span data-stu-id="3d975-120">Configuration Requirements</span></span>

<span data-ttu-id="3d975-121">將執行 Lync Server 2013 壓力與效能工具的電腦，必須依照下列需求進行設定：</span><span class="sxs-lookup"><span data-stu-id="3d975-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="3d975-122">您必須以網域或本機系統管理員群組的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="3d975-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="3d975-123">Lync Server 2013 應力和效能工具（LyncPerfTool）無法在同時執行 Lync Server 2013 元件的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="3d975-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="3d975-124">您必須在前端伺服器或使用者帳戶將駐留的標準版伺服器上執行 Lync Server 2013 使用者建立工具（UserProvisioningTool）。</span><span class="sxs-lookup"><span data-stu-id="3d975-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="3d975-125">當工具多次執行時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3d975-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="3d975-126">頁面檔案大小應由系統管理，或至少1.5 倍于系統的 RAM 數量。</span><span class="sxs-lookup"><span data-stu-id="3d975-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

