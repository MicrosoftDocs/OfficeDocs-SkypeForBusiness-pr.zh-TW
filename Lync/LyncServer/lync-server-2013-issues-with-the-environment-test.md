---
title: Lync Server 2013：環境測試的問題
description: Lync Server 2013：環境測試的問題。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574969"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="380de-103">Lync Server 2013 中環境測試的問題</span><span class="sxs-lookup"><span data-stu-id="380de-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="380de-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="380de-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="380de-105">最佳做法分析程式為您提供一種方法，讓您能夠驗證 Lync Server 2013 環境是否支援設定。</span><span class="sxs-lookup"><span data-stu-id="380de-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="380de-106">在 Active Directory 網域服務檢查過程中，最佳做法分析器會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="380de-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="380de-107">驗證 Active Directory 網域服務樹系和架構準備。</span><span class="sxs-lookup"><span data-stu-id="380de-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="380de-108">識別部署中的 Active Directory 網域服務網站和網域數目。</span><span class="sxs-lookup"><span data-stu-id="380de-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="380de-109">檢查樹系和網域層級。</span><span class="sxs-lookup"><span data-stu-id="380de-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="380de-110">檢查網域控制站版本。</span><span class="sxs-lookup"><span data-stu-id="380de-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="380de-111">識別網域、設定和架構命名內容。</span><span class="sxs-lookup"><span data-stu-id="380de-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="380de-112">識別啟用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="380de-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="380de-113">檢查全域 Active Directory 網域服務設定的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="380de-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="380de-114">檢查 Lync Server (Scp) 的服務連線點。</span><span class="sxs-lookup"><span data-stu-id="380de-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="380de-115">識別資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="380de-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="380de-116">解決環境中的問題</span><span class="sxs-lookup"><span data-stu-id="380de-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="380de-117">如果環境測試發現環境有問題，這些問題可能是由您的 Active Directory 設定或特定伺服器上執行的軟體層級問題所造成。</span><span class="sxs-lookup"><span data-stu-id="380de-117">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="380de-118">例如，如果最佳做法分析器識別出執行 Windows Server 2000 環境中的任何網域控制站，將會發出警告，而且您必須將這些網域控制站升級為支援的 Windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="380de-118">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

