---
title: Lync Server 2013：建構管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6997f64695a4df606e6fbaa9767f22be04de6615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="8d68c-102">Lync Server 2013 中的建構管理</span><span class="sxs-lookup"><span data-stu-id="8d68c-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d68c-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="8d68c-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="8d68c-104">[設定管理] 是記錄及追蹤硬體和軟體資產及系統設定資訊的程式。</span><span class="sxs-lookup"><span data-stu-id="8d68c-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="8d68c-105">它通常用來追蹤軟體授權、維護用戶端電腦和伺服器的標準硬體和軟體組建，以及定義新電腦的命名標準。</span><span class="sxs-lookup"><span data-stu-id="8d68c-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="8d68c-106">建構管理通常涵蓋下列類別：</span><span class="sxs-lookup"><span data-stu-id="8d68c-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="8d68c-107">**硬體**   ：此類別會追蹤 IT 組織擁有的裝置、裝置所在的位置，以及使用裝置的人員。</span><span class="sxs-lookup"><span data-stu-id="8d68c-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="8d68c-108">這項資訊可讓組織規劃和預算以進行升級、維護標準硬體組建、針對會計用途報告 IT 資產價值，並協助防範盜竊。</span><span class="sxs-lookup"><span data-stu-id="8d68c-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="8d68c-109">**軟體**   這個類別會追蹤安裝在每個電腦上的軟體、版本號碼，以及這些授權的保留位置。</span><span class="sxs-lookup"><span data-stu-id="8d68c-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="8d68c-110">此資訊可協助您規劃升級、確保軟體擁有授權，並偵測是否有未授權（與未經許可）的軟體。</span><span class="sxs-lookup"><span data-stu-id="8d68c-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="8d68c-111">**標準組建**   這個類別會追蹤用戶端電腦和伺服器的目前標準組建，以及用戶端電腦和伺服器是否符合此標準。</span><span class="sxs-lookup"><span data-stu-id="8d68c-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="8d68c-112">定義並強制執行標準組建可協助支援人員，因為員工必須只維持有限數量的每個軟體版本。</span><span class="sxs-lookup"><span data-stu-id="8d68c-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="8d68c-113">**累積更新與修正程式**   此類別會追蹤哪些 service pack 已測試並經過核准，且哪些電腦是最新的。</span><span class="sxs-lookup"><span data-stu-id="8d68c-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="8d68c-114">這項資訊對於降低電腦遭到破壞的風險，以及偵測已安裝未獲核准更新的使用者來說，是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="8d68c-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="8d68c-115">**系統設定資訊**   ：這個類別會追蹤系統的功能、系統元素之間的互動，以及依賴于正常執行的系統的進程。</span><span class="sxs-lookup"><span data-stu-id="8d68c-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="8d68c-116">例如，協力廠商 proxy 伺服器可以在單一伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="8d68c-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="8d68c-117">必須瞭解 proxy 伺服器對此伺服器的依賴性，而且如果發生失敗，可能也會需要應急方案。</span><span class="sxs-lookup"><span data-stu-id="8d68c-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="8d68c-118">如果 proxy 伺服器也可以設定為與其他前端伺服器通訊，相依性與應急方案可能會變更。</span><span class="sxs-lookup"><span data-stu-id="8d68c-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="8d68c-119">實施設定管理</span><span class="sxs-lookup"><span data-stu-id="8d68c-119">Implementing configuration management</span></span>

<span data-ttu-id="8d68c-120">在您決定需要管理哪些專案之後，請收集資料並報告資料來執行設定管理。</span><span class="sxs-lookup"><span data-stu-id="8d68c-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="8d68c-121">小型組織最簡單的方法就是手動收集資料（用戶端電腦、作業系統、已安裝軟體的數量及模型），並將它儲存在 Office Word 或 Office Excel 檔中。</span><span class="sxs-lookup"><span data-stu-id="8d68c-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="8d68c-122">對於較大、較複雜且不斷變更的系統，資產和詳細資訊的探索必須是自動化的。</span><span class="sxs-lookup"><span data-stu-id="8d68c-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="8d68c-123">決定與貴組織相關的資訊，並將其記錄在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="8d68c-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="8d68c-124">在下欄區域中，配置管理資料庫是支援人員和管理的公用程式：</span><span class="sxs-lookup"><span data-stu-id="8d68c-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="8d68c-125">**安全性審核**   ：資料庫可讓您找出執行 Lync Server 及用戶端電腦系統的伺服器，這些伺服器必須已套用熱修復程式，或已錯過安裝 service pack 或最新的防病毒更新。</span><span class="sxs-lookup"><span data-stu-id="8d68c-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="8d68c-126">**軟體安裝**   ：識別用戶端軟體版本並追蹤它們將協助系統管理員規劃版本更新與新的安裝，也可協助取得授權檔與合規性。</span><span class="sxs-lookup"><span data-stu-id="8d68c-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="8d68c-127">**配置資訊**   ：如果您維護的是所有設定的最新清單，且其預設值已變更，就能快速且更有效率地進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="8d68c-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="8d68c-128">**規劃升級**   如果容量審查發現您的 Lync 資料庫伺服器上需要額外的儲存空間，請務必知道每個伺服器是否都有內部 RAID 控制器。</span><span class="sxs-lookup"><span data-stu-id="8d68c-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="8d68c-129">如果有的話，那就是相同的模型嗎？</span><span class="sxs-lookup"><span data-stu-id="8d68c-129">If they do, then are they the same model?</span></span> <span data-ttu-id="8d68c-130">是否已安裝相同數量的磁片？</span><span class="sxs-lookup"><span data-stu-id="8d68c-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="8d68c-131">[設定管理] 資料庫會指出可以安裝的磁片類型、編號，以及每個案例中的升級路徑。</span><span class="sxs-lookup"><span data-stu-id="8d68c-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="8d68c-132">建構管理所用的工具</span><span class="sxs-lookup"><span data-stu-id="8d68c-132">Tools used for configuration management</span></span>

<span data-ttu-id="8d68c-133">您可以透過多種工具來探索、審核及報告資產。</span><span class="sxs-lookup"><span data-stu-id="8d68c-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="8d68c-134">本節將討論其中一些工具。</span><span class="sxs-lookup"><span data-stu-id="8d68c-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="8d68c-135">**自動腳本**   您可以撰寫簡單的腳本來報告諸如作業系統、service pack 層級等專案，以及軟體是否存在於特定電腦群組上。</span><span class="sxs-lookup"><span data-stu-id="8d68c-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="8d68c-136">您可以將這些腳本撰寫成組織的確切需求。</span><span class="sxs-lookup"><span data-stu-id="8d68c-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="8d68c-137">不過，所需的腳本數及其複雜性可能會使腳本的建立和維護成本高昂。</span><span class="sxs-lookup"><span data-stu-id="8d68c-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="8d68c-138">**自動化工具**   根據您的企業規模與組織的需求而定，您可能會想要考慮使用自動工具。</span><span class="sxs-lookup"><span data-stu-id="8d68c-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="8d68c-139">例如 Microsoft 端點設定管理員的工具會結合標準報表範本（例如 service pack 層級），也可讓您建立自訂的報表（例如自訂的應用程式）。</span><span class="sxs-lookup"><span data-stu-id="8d68c-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="8d68c-140">Microsoft 端點建構管理員也可以用來報告硬體和軟體設定。</span><span class="sxs-lookup"><span data-stu-id="8d68c-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="8d68c-141">與變更管理的關聯</span><span class="sxs-lookup"><span data-stu-id="8d68c-141">Relationship with change management</span></span>

<span data-ttu-id="8d68c-142">建構管理與變更管理密切相關。</span><span class="sxs-lookup"><span data-stu-id="8d68c-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="8d68c-143">[建構管理] 可識別變更的需求，並確認和記錄發生變更的情況。</span><span class="sxs-lookup"><span data-stu-id="8d68c-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="8d68c-144">例如，您可以使用配置管理資料庫來識別需要修復程式的伺服器。</span><span class="sxs-lookup"><span data-stu-id="8d68c-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="8d68c-145">變更管理然後定義應用程式的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d68c-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="8d68c-146">相反地，如果新的累加更新是推出，則變更管理程式應該會將此資訊提供給建構管理系統。</span><span class="sxs-lookup"><span data-stu-id="8d68c-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="8d68c-147">建構管理工具可能需要進行設定，以識別新的軟體，讓他們能夠探索並追蹤軟體部署的位置和時間。</span><span class="sxs-lookup"><span data-stu-id="8d68c-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

