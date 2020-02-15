---
title: '依類別的 Lync Server 2013: Lync Server cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5db33e3d41bca0a3d14361b6d7bda254d43d19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="f2a07-102">依類別的 Lync Server 2013 cmdlet</span><span class="sxs-lookup"><span data-stu-id="f2a07-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a07-103">_**主題上次修改日期：** 2017年-09-20 個_</span><span class="sxs-lookup"><span data-stu-id="f2a07-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="f2a07-104">Microsoft Lync Server 2013 隨附特別設計用來允許系統管理員可以從命令列管理 Lync Server 的幾乎 550 指令程式。</span><span class="sxs-lookup"><span data-stu-id="f2a07-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="f2a07-105">您從 Lync Server 管理命令介面存取指令程式。</span><span class="sxs-lookup"><span data-stu-id="f2a07-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="f2a07-106">您可以直接從命令列擷取某個 Cmdlet 的說明，方法為輸入類似下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2a07-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="f2a07-107">上述命令會擷取 **New-CsVoicePolicy** Cmdlet 所有可用的說明。</span><span class="sxs-lookup"><span data-stu-id="f2a07-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="f2a07-108">請將 **New-CsVoicePolicy** 的部分換成您要擷取說明的 Cmdlet 名稱。</span><span class="sxs-lookup"><span data-stu-id="f2a07-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="f2a07-109">若要擷取 cmdlet 可用於管理 Microsoft Lync Server 2013 的完整清單，請在 Lync Server 管理命令介面命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2a07-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="f2a07-p103">如果您不確定需要哪個 Cmdlet，我們也提供 Cmdlet 及其說明主題的分類清單。您會發現某些 Cmdlet 出現在多個類別中，這是刻意的設計，因為它們適用於產品的多個區域。以下是類別清單：</span><span class="sxs-lookup"><span data-stu-id="f2a07-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2a07-113">Skype for Business cmdlet 參照已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f2a07-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="f2a07-114">按一下下列連結將帶您前往 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f2a07-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="f2a07-115">內容現在是透過 GitHub 開啟來源，並可供社群參與。</span><span class="sxs-lookup"><span data-stu-id="f2a07-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="f2a07-116">參與有興趣嗎？</span><span class="sxs-lookup"><span data-stu-id="f2a07-116">Interested in contributing?</span></span> <span data-ttu-id="f2a07-117">請參閱 「 讀我檔案中的儲存機制：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="f2a07-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2a07-118">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f2a07-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2a07-119"><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 中的使用者管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-120"><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 中的語音應用程式 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a07-121"><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 中的用戶端管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 中的進階的 Enterprise Voice cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a07-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 中的 IM 和目前狀態 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 中的 PSTN 連線 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a07-125"><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 中的會議 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 的電話和裝置 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a07-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 中的基礎結構和部署 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 中的移轉和共存指令程式</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a07-129"><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 中的安全性指令程式</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server 2013 中的 Lync Server 管理命令介面組態 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a07-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 中的伺服器角色和服務 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-132"><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 中的行動性 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a07-133"><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 中的應用程式管理 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 中 persistent Chat Server cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2a07-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">同盟和 Lync Server 2013 中的外部存取 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f2a07-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 中的集中式的記錄 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2a07-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 中的 Enterprise Voice cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="f2a07-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2a07-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f2a07-138">See Also</span></span>


[<span data-ttu-id="f2a07-139">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="f2a07-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

