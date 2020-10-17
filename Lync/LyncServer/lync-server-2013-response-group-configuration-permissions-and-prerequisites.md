---
title: Lync Server 2013：回應群組設定許可權和必要條件
description: Lync Server 2013：回應群組設定許可權和必要條件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7a0548c1d8886eb7741d1a31b24b480c1a2d30f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560899"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="effec-103">Lync Server 2013 的回應群組設定許可權和必要條件</span><span class="sxs-lookup"><span data-stu-id="effec-103">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="effec-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="effec-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="effec-p101">「回應群組」是企業語音的一項通話管理功能。本主題說明設定回應群組之前需要具有的項目，以及執行設定工作所需的系統管理認證和權限。</span><span class="sxs-lookup"><span data-stu-id="effec-p101">Response Group is an Enterprise Voice call management feature. This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="effec-107">本節假設您已閱讀與回應群組相關的規劃文件。</span><span class="sxs-lookup"><span data-stu-id="effec-107">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="effec-108">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="effec-108">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="effec-109">設定工具與系統管理角色</span><span class="sxs-lookup"><span data-stu-id="effec-109">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="effec-110">您可以使用下列系統管理工具來設定回應群組：</span><span class="sxs-lookup"><span data-stu-id="effec-110">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="effec-111">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="effec-111">Lync Server Control Panel</span></span>

  - <span data-ttu-id="effec-112">回應群組設定工具</span><span class="sxs-lookup"><span data-stu-id="effec-112">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="effec-113">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="effec-113">Lync Server Management Shell</span></span>

<span data-ttu-id="effec-114">若要設定回應群組，您至少必須是下列其中一個系統管理角色的成員：</span><span class="sxs-lookup"><span data-stu-id="effec-114">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="effec-115"><strong>Active Directory 安全性群組 (1)</strong></span><span class="sxs-lookup"><span data-stu-id="effec-115"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-116">建立工作流程</span><span class="sxs-lookup"><span data-stu-id="effec-116">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="effec-117">指派管理員</span><span class="sxs-lookup"><span data-stu-id="effec-117">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="effec-118">建立/指派代理人和佇列</span><span class="sxs-lookup"><span data-stu-id="effec-118">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="effec-119">建立/管理假日和營業時間</span><span class="sxs-lookup"><span data-stu-id="effec-119">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="effec-120">啟用/停用工作流程</span><span class="sxs-lookup"><span data-stu-id="effec-120">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="effec-121">設定工作流程 (IVR 或群組搜尋)</span><span class="sxs-lookup"><span data-stu-id="effec-121">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="effec-122"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="effec-122"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-123">√</span><span class="sxs-lookup"><span data-stu-id="effec-123">√</span></span></p></td>
<td><p><span data-ttu-id="effec-124">√</span><span class="sxs-lookup"><span data-stu-id="effec-124">√</span></span></p></td>
<td><p><span data-ttu-id="effec-125">√</span><span class="sxs-lookup"><span data-stu-id="effec-125">√</span></span></p></td>
<td><p><span data-ttu-id="effec-126">√</span><span class="sxs-lookup"><span data-stu-id="effec-126">√</span></span></p></td>
<td><p><span data-ttu-id="effec-127">√</span><span class="sxs-lookup"><span data-stu-id="effec-127">√</span></span></p></td>
<td><p><span data-ttu-id="effec-128">√</span><span class="sxs-lookup"><span data-stu-id="effec-128">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="effec-129"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="effec-129"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="effec-130">√ (2) </span><span class="sxs-lookup"><span data-stu-id="effec-130">√(2)</span></span></p></td>
<td><p><span data-ttu-id="effec-131">√ (3) </span><span class="sxs-lookup"><span data-stu-id="effec-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="effec-132">√ (3) </span><span class="sxs-lookup"><span data-stu-id="effec-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="effec-133">√ (3) </span><span class="sxs-lookup"><span data-stu-id="effec-133">√(3)</span></span></p></td>
<td><p><span data-ttu-id="effec-134">√ (3) </span><span class="sxs-lookup"><span data-stu-id="effec-134">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="effec-135"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="effec-135"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-136">√</span><span class="sxs-lookup"><span data-stu-id="effec-136">√</span></span></p></td>
<td><p><span data-ttu-id="effec-137">√</span><span class="sxs-lookup"><span data-stu-id="effec-137">√</span></span></p></td>
<td><p><span data-ttu-id="effec-138">√</span><span class="sxs-lookup"><span data-stu-id="effec-138">√</span></span></p></td>
<td><p><span data-ttu-id="effec-139">√</span><span class="sxs-lookup"><span data-stu-id="effec-139">√</span></span></p></td>
<td><p><span data-ttu-id="effec-140">√</span><span class="sxs-lookup"><span data-stu-id="effec-140">√</span></span></p></td>
<td><p><span data-ttu-id="effec-141">√</span><span class="sxs-lookup"><span data-stu-id="effec-141">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="effec-142"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="effec-142"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-143">√</span><span class="sxs-lookup"><span data-stu-id="effec-143">√</span></span></p></td>
<td><p><span data-ttu-id="effec-144">√</span><span class="sxs-lookup"><span data-stu-id="effec-144">√</span></span></p></td>
<td><p><span data-ttu-id="effec-145">√</span><span class="sxs-lookup"><span data-stu-id="effec-145">√</span></span></p></td>
<td><p><span data-ttu-id="effec-146">√</span><span class="sxs-lookup"><span data-stu-id="effec-146">√</span></span></p></td>
<td><p><span data-ttu-id="effec-147">√</span><span class="sxs-lookup"><span data-stu-id="effec-147">√</span></span></p></td>
<td><p><span data-ttu-id="effec-148">√</span><span class="sxs-lookup"><span data-stu-id="effec-148">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="effec-149"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="effec-149"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-150">√</span><span class="sxs-lookup"><span data-stu-id="effec-150">√</span></span></p></td>
<td><p><span data-ttu-id="effec-151">√</span><span class="sxs-lookup"><span data-stu-id="effec-151">√</span></span></p></td>
<td><p><span data-ttu-id="effec-152">√</span><span class="sxs-lookup"><span data-stu-id="effec-152">√</span></span></p></td>
<td><p><span data-ttu-id="effec-153">√</span><span class="sxs-lookup"><span data-stu-id="effec-153">√</span></span></p></td>
<td><p><span data-ttu-id="effec-154">√</span><span class="sxs-lookup"><span data-stu-id="effec-154">√</span></span></p></td>
<td><p><span data-ttu-id="effec-155">√</span><span class="sxs-lookup"><span data-stu-id="effec-155">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="effec-156"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="effec-156"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="effec-157">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="effec-158">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="effec-159">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="effec-160">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="effec-161">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-161">√(4)</span></span></p></td>
<td><p><span data-ttu-id="effec-162">√ (4) </span><span class="sxs-lookup"><span data-stu-id="effec-162">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="effec-163"><STRONG> (1) </STRONG> Active Directory 網域服務使用者物件必須是所列指定之 Active Directory 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="effec-163"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="effec-164">具有適當許可權的系統管理員或其他委派的 Active Directory 群組成員，可將使用者新增至安全性群組中 (例如，系統管理員、帳戶操作員) 必須將使用者物件新增至所列的安全性群組或群組，使用者才能執行所列的功能。</span><span class="sxs-lookup"><span data-stu-id="effec-164">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="effec-165"><STRONG> (2) </STRONG> 僅適用于 CsResponseGroupAdministrator 已指定給 CsResponseGroupManager 的工作流程。</span><span class="sxs-lookup"><span data-stu-id="effec-165"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="effec-166"><STRONG> (3) </STRONG> 回應群組管理員可以將 CsResponseGroupManager 的另一個成員指派給目前管理員已管理的工作流程。</span><span class="sxs-lookup"><span data-stu-id="effec-166"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="effec-167"><STRONG> (4) </STRONG> CsViewOnlyAdministrator 只能執行動詞 "Get" Lync Server 管理命令介面 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="effec-167"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="effec-168">回應群組設定先決條件</span><span class="sxs-lookup"><span data-stu-id="effec-168">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="effec-169">回應群組需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="effec-169">Response Group requires the following components:</span></span>

  - <span data-ttu-id="effec-170">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="effec-170">Application service</span></span>

  - <span data-ttu-id="effec-171">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="effec-171">Response Group application</span></span>

  - <span data-ttu-id="effec-172">語言套件</span><span class="sxs-lookup"><span data-stu-id="effec-172">Language packs</span></span>

  - <span data-ttu-id="effec-173">檔案存放區 (用於保留音訊檔案)</span><span class="sxs-lookup"><span data-stu-id="effec-173">File store (to hold audio files)</span></span>

  - <span data-ttu-id="effec-174">Web 服務 (包含回應群組設定工具和代理程式的登入和登出主控台) </span><span class="sxs-lookup"><span data-stu-id="effec-174">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="effec-175">當您部署企業語音時，預設會安裝上述所有元件。</span><span class="sxs-lookup"><span data-stu-id="effec-175">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="effec-176">在設定回應群組之前，您可能需要先執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="effec-176">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="effec-177">為使用者啟用 Lync Server 2013 和 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="effec-177">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="effec-178">修改組態檔，以符合美國聯邦資訊處理標準 (FIPS)。</span><span class="sxs-lookup"><span data-stu-id="effec-178">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="effec-179">修改資料庫定序，以支援佇列名稱和代理人群組名稱中的 Yi、Meng 和 Zang 字元。</span><span class="sxs-lookup"><span data-stu-id="effec-179">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="effec-180">啟用使用者</span><span class="sxs-lookup"><span data-stu-id="effec-180">Enabling Users</span></span>

<span data-ttu-id="effec-181">設定回應群組的第一個步驟是建立代理人群組。</span><span class="sxs-lookup"><span data-stu-id="effec-181">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="effec-182">在您可以建立代理人群組之前，您必須啟用將成為 Lync Server 2013 和 Enterprise Voice 之回應群組之代理人的使用者。</span><span class="sxs-lookup"><span data-stu-id="effec-182">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="effec-183">為 Lync Server 2013 啟用使用者通常是 Enterprise Edition server 或 Standard Edition server 部署中的一個步驟。</span><span class="sxs-lookup"><span data-stu-id="effec-183">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="effec-184">如需對 Lync Server 2013 啟用使用者的詳細資訊，請參閱 [Disable or 重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="effec-184">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="effec-185">啟用使用者的企業語音一般是企業語音部署中的步驟。</span><span class="sxs-lookup"><span data-stu-id="effec-185">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="effec-186">如需詳細資訊，請參閱 [Enable users For Enterprise Voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="effec-186">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="effec-187">遵守 FIPS 要求</span><span class="sxs-lookup"><span data-stu-id="effec-187">Complying with FIPS requirements</span></span>

<span data-ttu-id="effec-188">只有在您的組織需要遵守美國聯邦資訊處理標準 (FIPS) 時，才適用本節內容。</span><span class="sxs-lookup"><span data-stu-id="effec-188">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="effec-189">若要遵守 FIPS，您需要修改應用程式層級的 Web.config 檔案，以在安裝 Web 服務後使用不同的密碼編譯演算法。</span><span class="sxs-lookup"><span data-stu-id="effec-189">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="effec-190">您需要指定 ASP.NET 使用三重資料加密標準 (3DES) 演算法來處理檢視狀態資料。</span><span class="sxs-lookup"><span data-stu-id="effec-190">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="effec-191">針對回應群組應用程式，此需求適用于回應群組設定工具和代理程式登入和登出主控台。</span><span class="sxs-lookup"><span data-stu-id="effec-191">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="effec-192">如需此需求的詳細資訊，請參閱 Microsoft 知識庫文章911722：「當您存取從 ASP.NET 1.1 升級為 ASP.NET 2.0 的 ASP.NET 網頁 ViewState 時，可能會收到錯誤訊息，"at] [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) 。</span><span class="sxs-lookup"><span data-stu-id="effec-192">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="effec-193">若要修改 Web.config 檔案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="effec-193">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="effec-194">在文字編輯器 (如 [記事本]) 中，開啟應用程式層級的 Web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="effec-194">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="effec-195">在 Web.config 檔案中，找出 `<system.web>` 區段。</span><span class="sxs-lookup"><span data-stu-id="effec-195">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="effec-196">`<machineKey>`在區段中新增下列區段 `<system.web>` ：</span><span class="sxs-lookup"><span data-stu-id="effec-196">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="effec-197">儲存 Web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="effec-197">Save the Web.config file.</span></span>

5.  <span data-ttu-id="effec-198">在命令提示字元中執行下列命令，以重新開機網際網路資訊服務 (IIS) 服務：</span><span class="sxs-lookup"><span data-stu-id="effec-198">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="effec-199">支援 Yi、Meng 和 Zang 字元</span><span class="sxs-lookup"><span data-stu-id="effec-199">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="effec-200">只有在您的組織需要支援 Yi、Meng 或 Zang 字元時，才適用本節內容。</span><span class="sxs-lookup"><span data-stu-id="effec-200">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="effec-201">如需有關彝語、Meng 及 Zang 字元的資訊及其可能對您的部署很重要的原因，請參閱 GB18030 字元集上的資訊 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> 。</span><span class="sxs-lookup"><span data-stu-id="effec-201">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="effec-p106">若要支援 Yi、Meng 或 Zang 字元，您需要修改 Rgsconfig 資料庫的定序。請變更每個 Rgsconfig 資料庫中下列各資料表內 **[名稱]** 資料行的定序：</span><span class="sxs-lookup"><span data-stu-id="effec-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="effec-204">Dbo。AgentGroups</span><span class="sxs-lookup"><span data-stu-id="effec-204">dbo.AgentGroups</span></span>

  - <span data-ttu-id="effec-205">Dbo。BusinessHours</span><span class="sxs-lookup"><span data-stu-id="effec-205">dbo.BusinessHours</span></span>

  - <span data-ttu-id="effec-206">Dbo。HolidaySets</span><span class="sxs-lookup"><span data-stu-id="effec-206">dbo.HolidaySets</span></span>

  - <span data-ttu-id="effec-207">Dbo。佇列</span><span class="sxs-lookup"><span data-stu-id="effec-207">dbo.Queues</span></span>

  - <span data-ttu-id="effec-208">Dbo。流程</span><span class="sxs-lookup"><span data-stu-id="effec-208">dbo.Workflows</span></span>

<span data-ttu-id="effec-209">針對 SQL Server 2008 R2 和 SQL Server 2012，使用拉丁語 \_ 一般 \_ 100 (區分重音) 歸類。</span><span class="sxs-lookup"><span data-stu-id="effec-209">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="effec-210">如果您使用此定序，則所有物件名稱都不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="effec-210">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="effec-211">您可以使用 Microsoft SQL Server Management Studio 來變更定序。</span><span class="sxs-lookup"><span data-stu-id="effec-211">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="effec-212">如需使用此工具的詳細資訊，請參閱「使用 SQL Server Management Studio」 [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) 。</span><span class="sxs-lookup"><span data-stu-id="effec-212">For details about using this tool, see "Using SQL Server Management Studio" at [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="effec-213">請遵循下列步驟來變更定序：</span><span class="sxs-lookup"><span data-stu-id="effec-213">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="effec-214">確定 SQL Server Management Studio 已設成允許需要重建資料表的變更。</span><span class="sxs-lookup"><span data-stu-id="effec-214">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="effec-215">如需詳細資訊，請參閱的「儲存 (不允許) 對話方塊」 [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) 。</span><span class="sxs-lookup"><span data-stu-id="effec-215">For details, see "Save (Not Permitted) Dialog Box" at [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="effec-216">如需設定欄歸類的詳細資訊，請參閱 how to： Set Column 歸類 (Visual Database Tools) "at" [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) 。</span><span class="sxs-lookup"><span data-stu-id="effec-216">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="effec-217">使用 Microsoft SQL Server Management Studio 連線至 Rgsconfig 資料庫。</span><span class="sxs-lookup"><span data-stu-id="effec-217">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="effec-218">在 Rgsconfig 資料庫中找到想要變更的資料表，並用滑鼠右鍵按一下資料表，然後按一下 **[設計]**。</span><span class="sxs-lookup"><span data-stu-id="effec-218">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="effec-219">變更 **[名稱]** 資料行的定序，然後儲存資料表。</span><span class="sxs-lookup"><span data-stu-id="effec-219">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

