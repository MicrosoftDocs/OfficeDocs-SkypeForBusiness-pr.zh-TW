---
title: Lync Server 2013：設定管理
description: Lync Server 2013：設定管理。
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
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552149"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="de7e4-103">Lync Server 2013 中的設定管理</span><span class="sxs-lookup"><span data-stu-id="de7e4-103">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7e4-104">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="de7e4-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="de7e4-105">設定管理是一種記錄和追蹤硬體和軟體資產及系統設定資訊的處理常式。</span><span class="sxs-lookup"><span data-stu-id="de7e4-105">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="de7e4-106">通常是用來追蹤軟體授權、維護用戶端電腦和伺服器的標準硬體和軟體組建，以及定義新電腦的命名標準。</span><span class="sxs-lookup"><span data-stu-id="de7e4-106">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="de7e4-107">設定管理通常涵蓋下列類別：</span><span class="sxs-lookup"><span data-stu-id="de7e4-107">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="de7e4-108">**硬體**    此類別會追蹤 IT 組織所擁有的設備元件、裝置所在位置，以及使用設備的人員。</span><span class="sxs-lookup"><span data-stu-id="de7e4-108">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="de7e4-109">這項資訊可讓組織規劃及預算升級、維護標準硬體組建、報告 IT 資產的價值以進行會計目的，以及協助防止盜竊。</span><span class="sxs-lookup"><span data-stu-id="de7e4-109">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="de7e4-110">**軟體**    此類別會追蹤安裝在每一部電腦上的軟體、版本號碼，以及授權的持有位置。</span><span class="sxs-lookup"><span data-stu-id="de7e4-110">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="de7e4-111">此資訊可協助您規劃升級，以確保軟體取得授權，並偵測是否存在未授權的 (和未經許可的) 軟體。</span><span class="sxs-lookup"><span data-stu-id="de7e4-111">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="de7e4-112">**標準組建**    此類別會為用戶端電腦和伺服器追蹤目前的標準組建，以及用戶端電腦和伺服器是否符合此標準。</span><span class="sxs-lookup"><span data-stu-id="de7e4-112">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="de7e4-113">定義及強制執行標準組建可協助支援人員，因為員工只需要維護一份軟體的有限數目的版本。</span><span class="sxs-lookup"><span data-stu-id="de7e4-113">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="de7e4-114">**累計更新和修復程式**    此類別會追蹤哪些 service pack 已測試並核准使用，以及哪些電腦是最新的。</span><span class="sxs-lookup"><span data-stu-id="de7e4-114">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="de7e4-115">這項資訊對於降低遭到損害的電腦風險及偵測已安裝未獲批准之更新的使用者來說很重要。</span><span class="sxs-lookup"><span data-stu-id="de7e4-115">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="de7e4-116">**系統組態資訊**    此類別會追蹤系統的功能、系統元素之間的互動，以及取決於執行順利之系統的處理常式。</span><span class="sxs-lookup"><span data-stu-id="de7e4-116">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="de7e4-117">例如，您可以在單一伺服器上設定協力廠商 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="de7e4-117">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="de7e4-118">應瞭解 proxy 伺服器對此伺服器的依賴性，如果失敗，可能需要應變計劃。</span><span class="sxs-lookup"><span data-stu-id="de7e4-118">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="de7e4-119">如果可將 proxy 伺服器設定為同時與其他前端伺服器通訊，則相依性和應急計畫可能會變更。</span><span class="sxs-lookup"><span data-stu-id="de7e4-119">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="de7e4-120">實施設定管理</span><span class="sxs-lookup"><span data-stu-id="de7e4-120">Implementing configuration management</span></span>

<span data-ttu-id="de7e4-121">決定需要管理的專案後，請透過收集資料和報告資料來執行設定管理。</span><span class="sxs-lookup"><span data-stu-id="de7e4-121">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="de7e4-122">小型組織最簡單的方法，就是以手動方式收集資料 (用戶端電腦的數目和模型，作業系統，已安裝軟體) ，並將其儲存在 Office Word 或 Office Excel 檔中。</span><span class="sxs-lookup"><span data-stu-id="de7e4-122">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="de7e4-123">針對較大型、更複雜且經常變更的系統，資產和詳細資訊集合的探索必須是自動化的。</span><span class="sxs-lookup"><span data-stu-id="de7e4-123">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="de7e4-124">決定組織的相關資訊，並將其記錄在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="de7e4-124">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="de7e4-125">在下列方面，設定管理資料庫是支援人員和管理的有用工具：</span><span class="sxs-lookup"><span data-stu-id="de7e4-125">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="de7e4-126">**安全性審核**    資料庫可讓您識別執行 Lync Server 的伺服器，以及必須套用修補程式或已錯過安裝 service pack 或最新防病毒更新安裝之用戶端電腦系統的伺服器。</span><span class="sxs-lookup"><span data-stu-id="de7e4-126">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="de7e4-127">**軟體安裝**    識別用戶端軟體版本並加以追蹤，會協助系統管理員規劃版本更新及新的安裝，也會協助授權檔和符合性。</span><span class="sxs-lookup"><span data-stu-id="de7e4-127">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="de7e4-128">設定**資訊**    如果您維護所有已變更其預設值之設定的最新清單，您將能夠快速且有效地疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="de7e4-128">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="de7e4-129">**規劃升級**    如果容量審查顯示您的 Lync 資料庫伺服器需要額外的儲存空間，請務必知道每個伺服器是否都有內部 RAID 控制器。</span><span class="sxs-lookup"><span data-stu-id="de7e4-129">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="de7e4-130">如果是的話，就是相同的模型？</span><span class="sxs-lookup"><span data-stu-id="de7e4-130">If they do, then are they the same model?</span></span> <span data-ttu-id="de7e4-131">是否已安裝相同數目的磁片？</span><span class="sxs-lookup"><span data-stu-id="de7e4-131">Do they have the same number of disks installed?</span></span> <span data-ttu-id="de7e4-132">設定管理資料庫會指出可以安裝的磁片類型、編號，以及每個案例中的升級路徑。</span><span class="sxs-lookup"><span data-stu-id="de7e4-132">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="de7e4-133">設定管理所使用的工具</span><span class="sxs-lookup"><span data-stu-id="de7e4-133">Tools used for configuration management</span></span>

<span data-ttu-id="de7e4-134">有許多工具可用於探索、審計及報告資產。</span><span class="sxs-lookup"><span data-stu-id="de7e4-134">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="de7e4-135">本節將討論其中的部分工具。</span><span class="sxs-lookup"><span data-stu-id="de7e4-135">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="de7e4-136">**自動化腳本**    您可以撰寫簡易腳本來報告諸如作業系統、service pack 層級等專案，以及特定電腦群組的軟體是否存在。</span><span class="sxs-lookup"><span data-stu-id="de7e4-136">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="de7e4-137">您可以將這些腳本撰寫為組織的確切需求。</span><span class="sxs-lookup"><span data-stu-id="de7e4-137">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="de7e4-138">不過，必要的腳本數目及其複雜性可能會使腳本的建立和維護成本高。</span><span class="sxs-lookup"><span data-stu-id="de7e4-138">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="de7e4-139">**自動化工具**    視您的業務規模和組織需求而定，您可能會想要考慮使用自動工具。</span><span class="sxs-lookup"><span data-stu-id="de7e4-139">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="de7e4-140">Microsoft 端點 Configuration Manager 等工具會結合標準報表範本 (例如 service pack 層級) ，也可讓您建立自訂報告（例如，針對自訂應用程式）。</span><span class="sxs-lookup"><span data-stu-id="de7e4-140">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="de7e4-141">Microsoft 端點 Configuration Manager 也可以用來報告硬體和軟體設定。</span><span class="sxs-lookup"><span data-stu-id="de7e4-141">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="de7e4-142">與變更管理的關聯</span><span class="sxs-lookup"><span data-stu-id="de7e4-142">Relationship with change management</span></span>

<span data-ttu-id="de7e4-143">設定管理與變更管理密切相關。</span><span class="sxs-lookup"><span data-stu-id="de7e4-143">Configuration management is closely related to change management.</span></span> <span data-ttu-id="de7e4-144">設定管理可識別變更的需求，並識別及記錄發生變更的情況。</span><span class="sxs-lookup"><span data-stu-id="de7e4-144">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="de7e4-145">例如，設定管理資料庫可用於識別需要修復程式的伺服器。</span><span class="sxs-lookup"><span data-stu-id="de7e4-145">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="de7e4-146">變更管理會定義套用修復程式的程式。</span><span class="sxs-lookup"><span data-stu-id="de7e4-146">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="de7e4-147">相反地，如果新的累計更新已滾出，變更管理程式應將此資訊提供給設定管理系統。</span><span class="sxs-lookup"><span data-stu-id="de7e4-147">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="de7e4-148">設定管理工具可能需要加以設定，以識別新的軟體，讓他們能夠探索及追蹤軟體的部署位置和時間。</span><span class="sxs-lookup"><span data-stu-id="de7e4-148">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

