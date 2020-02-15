---
title: 環境測試的 Lync Server 2013： 問題
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
ms.openlocfilehash: b7d077b22c147dd677a5db68636b2c68bfafcf23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="ebc42-102">環境測試 Lync Server 2013 中的問題</span><span class="sxs-lookup"><span data-stu-id="ebc42-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc42-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="ebc42-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ebc42-104">最佳做法分析程式可讓您確認您的 Lync Server 2013 環境是支援的組態。</span><span class="sxs-lookup"><span data-stu-id="ebc42-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="ebc42-105">[Active Directory 網域服務檢查的一部分，最佳做法分析程式會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ebc42-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="ebc42-106">驗證的 Active Directory 網域服務樹系和結構描述準備工作。</span><span class="sxs-lookup"><span data-stu-id="ebc42-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="ebc42-107">識別 Active Directory 網域服務網站及網域中部署的數目。</span><span class="sxs-lookup"><span data-stu-id="ebc42-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="ebc42-108">檢查樹系與網域層級。</span><span class="sxs-lookup"><span data-stu-id="ebc42-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="ebc42-109">檢查網域控制器版本。</span><span class="sxs-lookup"><span data-stu-id="ebc42-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="ebc42-110">識別網域、 設定及 schema 命名內容。</span><span class="sxs-lookup"><span data-stu-id="ebc42-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="ebc42-111">會識別已啟用的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="ebc42-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="ebc42-112">檢查儲存全域 Active Directory 網域服務設定。</span><span class="sxs-lookup"><span data-stu-id="ebc42-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="ebc42-113">Lync Server 的服務連線點 (Scp) 檢查。</span><span class="sxs-lookup"><span data-stu-id="ebc42-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="ebc42-114">識別資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="ebc42-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="ebc42-115">解決環境問題。</span><span class="sxs-lookup"><span data-stu-id="ebc42-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="ebc42-116">如果環境測試找到您的環境的問題，這些問題都可能會因您的 Active Directory 設定] 或 [特定伺服器上執行的軟體的層級的問題。</span><span class="sxs-lookup"><span data-stu-id="ebc42-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="ebc42-117">例如，如果最佳做法分析程式識別正在執行 Windows Server 2000 任何網域控制站您環境中的，它會發出警告和您想要將這些網域控制站升級至支援的 Windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="ebc42-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

