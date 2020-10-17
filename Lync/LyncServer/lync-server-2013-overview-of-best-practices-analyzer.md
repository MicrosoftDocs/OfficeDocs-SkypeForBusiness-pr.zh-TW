---
title: Lync Server 2013：最佳做法分析器簡介
description: Lync Server 2013：最佳做法分析器簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ea48e88b26fa1081e5770fef2ac24efc21b74cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559279"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="641e6-103">Lync Server 2013 中的最佳做法分析程式概述</span><span class="sxs-lookup"><span data-stu-id="641e6-103">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="641e6-104">_**主題上次修改日期：** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="641e6-104">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="641e6-105">您可以使用 Lync Server 2013，最佳做法分析程式來找出並解決您的 Lync Server 2013 部署問題。</span><span class="sxs-lookup"><span data-stu-id="641e6-105">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="641e6-106">Lync Server 2013，最佳做法分析器會收集 Lync Server 2013 元件的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="641e6-106">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="641e6-107">透過適當的網路存取，最佳作法分析程式可以檢查執行 Active Directory 網域服務、Exchange Server 整合通訊 (UM) 和 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="641e6-107">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="641e6-108">您可以使用最佳做法分析程式來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="641e6-108">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="641e6-109">主動執行檢查，確認設定是根據建議的最佳作法進行設定。</span><span class="sxs-lookup"><span data-stu-id="641e6-109">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="641e6-110">自動偵測 Lync Server 2013 所需的更新。</span><span class="sxs-lookup"><span data-stu-id="641e6-110">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="641e6-111">產生問題的清單，例如，不理想的設定、不支援的選項、遺失的更新或不建議使用的作法。</span><span class="sxs-lookup"><span data-stu-id="641e6-111">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="641e6-112">協助您疑難排解並修正特定問題。</span><span class="sxs-lookup"><span data-stu-id="641e6-112">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="641e6-113">最佳做法分析程式可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="641e6-113">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="641e6-114">最低安裝必要條件。</span><span class="sxs-lookup"><span data-stu-id="641e6-114">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="641e6-115">有關報告問題的線上檔，包括疑難排解秘訣。</span><span class="sxs-lookup"><span data-stu-id="641e6-115">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="641e6-116">您可以儲存以供日後複查的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="641e6-116">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="641e6-117">一流的系統分析。</span><span class="sxs-lookup"><span data-stu-id="641e6-117">State-of-the-art system analysis.</span></span>

<span data-ttu-id="641e6-118">最佳做法分析程式會使用一組 XML 設定檔，判斷要從 Lync Server 2013 環境收集的資訊。</span><span class="sxs-lookup"><span data-stu-id="641e6-118">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="641e6-119">除了檢查 Active Directory 網域服務之外，它還會檢查來源，例如 windows Management Instrumentation (WMI) 中的 Windows Server 作業系統註冊表和設定。</span><span class="sxs-lookup"><span data-stu-id="641e6-119">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="641e6-120">最佳做法分析程式會比較針對 Lync Server 2013 部署設定和設定的一組預先定義的規則所收集的資料。</span><span class="sxs-lookup"><span data-stu-id="641e6-120">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="641e6-121">在比較收集的資料與預先定義的規則之後，該工具會報告問題。</span><span class="sxs-lookup"><span data-stu-id="641e6-121">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="641e6-122">[！附注] 針對報告的每個問題，最佳做法分析器會提供有關掃描的 Lync Server 2013 環境中所找到之專案的相關資訊，以及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="641e6-122">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="641e6-123">最佳做法分析程式也提供有關特定問題的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="641e6-123">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="641e6-124">Lync Server 2013，最佳作法 Analyzer 只會收集 Lync Server 2013 元件的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="641e6-124">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="641e6-125">您可以使用舊版的工具來掃描先前的環境。</span><span class="sxs-lookup"><span data-stu-id="641e6-125">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="641e6-126">如需詳細資訊，請參閱 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">在 Lync Server 2013 中執行最佳做法分析程式的需求</A>。</span><span class="sxs-lookup"><span data-stu-id="641e6-126">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

