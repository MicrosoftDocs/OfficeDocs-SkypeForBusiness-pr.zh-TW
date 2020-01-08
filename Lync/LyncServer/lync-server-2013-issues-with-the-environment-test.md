---
title: Lync Server 2013：環境測試的問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="a1aea-102">Lync Server 2013 中的環境測試問題</span><span class="sxs-lookup"><span data-stu-id="a1aea-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1aea-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a1aea-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a1aea-104">最佳做法分析程式提供一種驗證 Lync Server 2013 環境是否支援設定的方式。</span><span class="sxs-lookup"><span data-stu-id="a1aea-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="a1aea-105">在 Active Directory 網域服務檢查中，最佳做法分析程式會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1aea-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="a1aea-106">驗證 Active Directory 網域服務林及架構準備。</span><span class="sxs-lookup"><span data-stu-id="a1aea-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="a1aea-107">識別部署中 Active Directory 網域服務網站和網域的數目。</span><span class="sxs-lookup"><span data-stu-id="a1aea-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="a1aea-108">檢查目錄林及網域層級。</span><span class="sxs-lookup"><span data-stu-id="a1aea-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="a1aea-109">檢查網網域控制站版本。</span><span class="sxs-lookup"><span data-stu-id="a1aea-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="a1aea-110">識別網域、配置和架構命名內容。</span><span class="sxs-lookup"><span data-stu-id="a1aea-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="a1aea-111">標識已啟用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a1aea-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="a1aea-112">檢查全域 Active Directory 網域服務設定的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="a1aea-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="a1aea-113">檢查 Lync Server 的服務連接點（SCPs）。</span><span class="sxs-lookup"><span data-stu-id="a1aea-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="a1aea-114">識別資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="a1aea-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="a1aea-115">解決環境問題</span><span class="sxs-lookup"><span data-stu-id="a1aea-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="a1aea-116">如果環境測試發現您的環境有問題，這些問題可能是由您的 Active Directory 設定或特定伺服器上執行的軟體層級問題所造成。</span><span class="sxs-lookup"><span data-stu-id="a1aea-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="a1aea-117">例如，如果最佳做法分析程式發現您環境中執行 Windows Server 2000 的任何網網域控制站，都會發出警告，而且您必須將這些網網域控制站升級為受支援版本的 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="a1aea-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

