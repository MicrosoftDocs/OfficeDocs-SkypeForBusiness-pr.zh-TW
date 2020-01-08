---
title: Lync Server 2013：準備 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="d785a-102">在 Lync Server 2013 中準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="d785a-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d785a-103">_**主題上次修改日期：** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="d785a-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="d785a-104">在 Lync Server 2013 中，您可以使用 Lync Server 部署嚮導來準備 Active Directory 網域服務，或者您可以直接使用 Lync Server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d785a-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="d785a-105">您也可以直接在網網域控制站上使用 ldifde 命令列工具，如本主題稍後所述。</span><span class="sxs-lookup"><span data-stu-id="d785a-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="d785a-106">Lync Server 部署嚮導會引導您完成每個 Active Directory 準備工作。</span><span class="sxs-lookup"><span data-stu-id="d785a-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="d785a-107">[部署嚮導] 會執行 Lync Server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d785a-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="d785a-108">此工具適用于只有單一網域和單一林拓撲或其他類似拓撲的環境。</span><span class="sxs-lookup"><span data-stu-id="d785a-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d785a-109">您可以在網域或網域中部署 Lync Server，該網域控制站會執行32位版本的作業系統（如需詳細資訊，請參閱<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 的 Active Directory 基礎結構需求</A>）。</span><span class="sxs-lookup"><span data-stu-id="d785a-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="d785a-110">不過，您無法使用 Lync Server 部署嚮導在這些環境中執行架構、林及網域準備，因為部署嚮導和支援檔案只有64位。</span><span class="sxs-lookup"><span data-stu-id="d785a-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="d785a-111">相反地，您可以在32位網網域控制站上使用 ldifde 和相關聯的 .ldf 檔案，以準備架構、林及網域。</span><span class="sxs-lookup"><span data-stu-id="d785a-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="d785a-112">請參閱本主題稍後的「使用 Cmdlet 與 cscript.exe」一節。</span><span class="sxs-lookup"><span data-stu-id="d785a-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="d785a-113">您可以使用 Lync Server 管理命令介面 Cmdlet 來遠端或更複雜的環境執行工作。</span><span class="sxs-lookup"><span data-stu-id="d785a-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="d785a-114">Active Directory 準備先決條件</span><span class="sxs-lookup"><span data-stu-id="d785a-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="d785a-115">您必須在執行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 （含 SP1 （64））的電腦上執行 Active Directory 準備步驟。</span><span class="sxs-lookup"><span data-stu-id="d785a-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="d785a-116">Active Directory 準備需要 Lync Server Management 命令介面和 OCSCore。</span><span class="sxs-lookup"><span data-stu-id="d785a-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="d785a-117">必須具備下列元件，才能執行 Active Directory 準備工作：</span><span class="sxs-lookup"><span data-stu-id="d785a-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="d785a-118">Lync Server 核心元件（OCScore）</span><span class="sxs-lookup"><span data-stu-id="d785a-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d785a-119">如果您打算使用 Lync Server 管理命令介面進行 Active Directory 準備，您必須先執行 Lync Server 部署嚮導，才能安裝核心元件。</span><span class="sxs-lookup"><span data-stu-id="d785a-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="d785a-120">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="d785a-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d785a-121">針對 Windows Server 2012 和 Windows Server 2012 R2，您可以使用 Server Manager 來安裝並啟動 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="d785a-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="d785a-122">如需詳細資訊，請參閱<A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他軟體需求</A>中的 "Microsoft .net Framework 4.5"。</span><span class="sxs-lookup"><span data-stu-id="d785a-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="d785a-123">若是 Windows Server&nbsp;2008&nbsp;R2，請從 Microsoft 網站下載並安裝<A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A> 。</span><span class="sxs-lookup"><span data-stu-id="d785a-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="d785a-124">遠端伺服器管理工具（RSAT）</span><span class="sxs-lookup"><span data-stu-id="d785a-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d785a-125">如果您在成員伺服器而不是在網網域控制站上執行 Active Directory 準備步驟，則需要使用一些 RSAT 工具。</span><span class="sxs-lookup"><span data-stu-id="d785a-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="d785a-126">從 [伺服器管理員] 中的 [AD DS] 和 [AD LDS 工具] 節點，安裝 AD DS 的管理單元和命令列工具，以及適用于 Windows PowerShell 的 Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="d785a-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="d785a-127">Microsoft Visual c + + 11 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="d785a-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d785a-128">如果電腦上尚未安裝此必備元件，安裝程式會提示您安裝。</span><span class="sxs-lookup"><span data-stu-id="d785a-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="d785a-129">套件是為您提供的，您不需要單獨取得套件。</span><span class="sxs-lookup"><span data-stu-id="d785a-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="d785a-130">Windows PowerShell 3.0 （64位）</span><span class="sxs-lookup"><span data-stu-id="d785a-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="d785a-131">針對 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 應該包含在您的 Lync Server 2013 安裝中。</span><span class="sxs-lookup"><span data-stu-id="d785a-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="d785a-132">若是 Windows Server 2008 R2，您需要安裝或升級至 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="d785a-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="d785a-133">如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="d785a-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="d785a-134">系統管理員權力與角色</span><span class="sxs-lookup"><span data-stu-id="d785a-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="d785a-135">下表顯示每個 Active Directory 準備工作所需的管理許可權和角色。</span><span class="sxs-lookup"><span data-stu-id="d785a-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="d785a-136">Active Directory 準備所需的使用者權利</span><span class="sxs-lookup"><span data-stu-id="d785a-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d785a-137">過程</span><span class="sxs-lookup"><span data-stu-id="d785a-137">Procedure</span></span></th>
<th><span data-ttu-id="d785a-138">權力或角色</span><span class="sxs-lookup"><span data-stu-id="d785a-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d785a-139">架構準備</span><span class="sxs-lookup"><span data-stu-id="d785a-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="d785a-140">目錄林根網域的架構管理員群組的成員，以及架構主機上的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="d785a-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d785a-141">林準備</span><span class="sxs-lookup"><span data-stu-id="d785a-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="d785a-142">林的 [企業管理員] 群組成員</span><span class="sxs-lookup"><span data-stu-id="d785a-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d785a-143">網域準備</span><span class="sxs-lookup"><span data-stu-id="d785a-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="d785a-144">指定網域的 [企業管理員] 或 [網域管理員] 群組成員</span><span class="sxs-lookup"><span data-stu-id="d785a-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="d785a-145">Active Directory 準備 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d785a-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="d785a-146">下表將用來準備 AD DS 的 Lync Server 管理命令介面 Cmdlet 與用來在 Microsoft Office 通訊伺服器 2007 R2 中用來準備 AD DS 的 LcsCmd 命令進行比較。</span><span class="sxs-lookup"><span data-stu-id="d785a-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="d785a-147">與 LcsCmd 比較的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d785a-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d785a-148">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d785a-148">Cmdlets</span></span></th>
<th><span data-ttu-id="d785a-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="d785a-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d785a-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d785a-151">Lcscmd/forest/action： SchemaPrep/SchemaType： Server</span><span class="sxs-lookup"><span data-stu-id="d785a-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d785a-152">CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="d785a-153">Lcscmd/forest/action： CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="d785a-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d785a-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d785a-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d785a-155">Lcscmd/forest/action： ForestPrep</span><span class="sxs-lookup"><span data-stu-id="d785a-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d785a-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d785a-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d785a-157">Lcscmd/forest/action： ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="d785a-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d785a-158">CsAdForest</span><span class="sxs-lookup"><span data-stu-id="d785a-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="d785a-159">Lcscmd/forest/action： CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="d785a-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d785a-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d785a-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d785a-161">Lcscmd/domain/action： [已準備]</span><span class="sxs-lookup"><span data-stu-id="d785a-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d785a-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d785a-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d785a-163">Lcscmd/domain/action： DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="d785a-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d785a-164">CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="d785a-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="d785a-165">Lcscmd/domain/action： CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="d785a-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="d785a-166">已鎖定 Active Directory 需求</span><span class="sxs-lookup"><span data-stu-id="d785a-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="d785a-167">如果您的組織中必須停用 [許可權繼承] 或 [驗證的使用者] 許可權，您必須在網域準備期間執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="d785a-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="d785a-168">如需詳細資訊，請參閱[在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d785a-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="d785a-169">自訂容器許可權</span><span class="sxs-lookup"><span data-stu-id="d785a-169">Custom Container Permissions</span></span>

<span data-ttu-id="d785a-170">如果您的組織使用的是自訂容器，而不是三個內建的容器（也就是使用者、電腦及網網域控制站），您必須為 [已驗證使用者] 群組的自訂容器授與讀取權限。</span><span class="sxs-lookup"><span data-stu-id="d785a-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="d785a-171">網域準備必須具備容器的讀取權。</span><span class="sxs-lookup"><span data-stu-id="d785a-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="d785a-172">如需詳細資訊，請參閱[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="d785a-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="d785a-173">使用 Cmdlet 和 Ldifde</span><span class="sxs-lookup"><span data-stu-id="d785a-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="d785a-174">Lync Server 部署嚮導中的 [**準備架構**] 步驟，且**安裝 CsAdServerSchema** Cmdlet 會在執行64位作業系統的網網域控制站上延伸 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="d785a-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="d785a-175">如果您需要在執行32位作業系統的網網域控制站上延伸 Active Directory 架構，您可以從成員伺服器遠端執行**安裝 CsAdServerSchema** Cmdlet （建議的方法）。</span><span class="sxs-lookup"><span data-stu-id="d785a-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="d785a-176">不過，如果您需要直接在網網域控制站上執行架構準備，您可以使用 Ldifde 工具匯入架構檔案。</span><span class="sxs-lookup"><span data-stu-id="d785a-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="d785a-177">Ldifde 工具隨附于大多數版本的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="d785a-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="d785a-178">如果您使用 Ldifde 匯入架構檔案，無論您是從舊版本進行遷移或執行全新安裝，都必須匯入所有四個檔案。</span><span class="sxs-lookup"><span data-stu-id="d785a-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="d785a-179">您必須以下列順序匯入它們：</span><span class="sxs-lookup"><span data-stu-id="d785a-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="d785a-180">ExternalSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="d785a-181">ServerSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="d785a-182">BackCompatSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="d785a-183">VersionSchema</span><span class="sxs-lookup"><span data-stu-id="d785a-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d785a-184">四個 .ldf 檔案位於您的安裝媒體或下載的 \Support\Schema 目錄中。</span><span class="sxs-lookup"><span data-stu-id="d785a-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="d785a-185">若要使用 Ldifde 匯入架構主機所在的網網域控制站上的四個架構檔案，請使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="d785a-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="d785a-186">例如：</span><span class="sxs-lookup"><span data-stu-id="d785a-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="d785a-187">如果您是以不同的使用者身分登入，請使用 b 參數。</span><span class="sxs-lookup"><span data-stu-id="d785a-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="d785a-188">如需有關所需使用者許可權的詳細資訊，請參閱本主題先前的「管理員權力與角色」一節。</span><span class="sxs-lookup"><span data-stu-id="d785a-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="d785a-189">若要使用 Ldifde 匯入非架構主機的網網域控制站上的四個架構檔案，請使用下列格式：</span><span class="sxs-lookup"><span data-stu-id="d785a-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="d785a-190">如需使用 Ldifde 的詳細資訊，請參閱 Microsoft 知識庫文章237677：「使用 LDIFDE 將目錄物件匯入及匯出到 Active Directory [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)」。</span><span class="sxs-lookup"><span data-stu-id="d785a-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d785a-191">本節內容</span><span class="sxs-lookup"><span data-stu-id="d785a-191">In This Section</span></span>

  - [<span data-ttu-id="d785a-192">在 Lync Server 2013 中準備 Active Directory 結構描述</span><span class="sxs-lookup"><span data-stu-id="d785a-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="d785a-193">為 Lync Server 2013 準備樹系</span><span class="sxs-lookup"><span data-stu-id="d785a-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="d785a-194">針對 Lync Server 2013 準備網域</span><span class="sxs-lookup"><span data-stu-id="d785a-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

