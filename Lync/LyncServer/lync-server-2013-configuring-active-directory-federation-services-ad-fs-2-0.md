---
title: 'Lync Server 2013：設定 Active Directory Federation Services (AD FS 2.0) '
description: Lync Server 2013：設定 Active Directory Federation Services (AD FS 2.0) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc21500273d8576f54f6110783e61764ec9723a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567839"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="518ca-103">為 Lync Server 2013 設定 Active Directory Federation Services (AD FS 2.0) </span><span class="sxs-lookup"><span data-stu-id="518ca-103">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="518ca-104">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="518ca-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="518ca-105">下列章節說明如何設定 Active Directory Federation Services (AD FS 2.0) 以支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="518ca-105">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="518ca-106">如需如何安裝 AD FS 2.0 的詳細資訊，請參閱《 AD FS 2.0 逐步逐步說明》 [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) 。</span><span class="sxs-lookup"><span data-stu-id="518ca-106">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="518ca-107">安裝 AD FS 2.0 時，請勿使用 Windows Server 管理員來新增 Active Directory Federation Services 角色。</span><span class="sxs-lookup"><span data-stu-id="518ca-107">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="518ca-108">請改為在上下載並安裝 Active Directory Federation Services 2.0 幫手 RTW 套件 <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> 。</span><span class="sxs-lookup"><span data-stu-id="518ca-108">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="518ca-109">**設定用於雙因素驗證的 AD FS**</span><span class="sxs-lookup"><span data-stu-id="518ca-109">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="518ca-110">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="518ca-110">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="518ca-111">啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="518ca-111">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="518ca-112">在 [Windows PowerShell] 命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="518ca-112">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="518ca-113">使用 Lync Server 2013 的累計更新，建立與每個 Lync Server 2013 的合作關係：7月 2013 Director、Enterprise Pool 和 Standard Edition Server，可執行下列命令取代專用於您的部署的伺服器名稱，以供啟用被動驗證：</span><span class="sxs-lookup"><span data-stu-id="518ca-113">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="518ca-114">在 [系統管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="518ca-114">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="518ca-115">展開 [ **信任關係** \> **信賴**憑證者信任]。</span><span class="sxs-lookup"><span data-stu-id="518ca-115">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="518ca-116">請確認已為您的 Lync Server 2013 建立新的信任，其具有 Lync Server 2013 的累計更新：7月 2013 Enterprise Pool 或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="518ca-116">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="518ca-117">執行下列命令，為使用 Windows PowerShell 的信賴憑證者信任建立並指派發行授權規則：</span><span class="sxs-lookup"><span data-stu-id="518ca-117">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="518ca-118">執行下列命令，為您使用 Windows PowerShell 建立並指派「信賴憑證方信任」的發行轉換規則：</span><span class="sxs-lookup"><span data-stu-id="518ca-118">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="518ca-119">在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下您的信賴憑證者信任，然後選取 [ **編輯宣告規則**]。</span><span class="sxs-lookup"><span data-stu-id="518ca-119">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="518ca-120">選取 [ **發行授權規則** ] 索引標籤，並確認已成功建立新的授權規則。</span><span class="sxs-lookup"><span data-stu-id="518ca-120">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="518ca-121">選取 [ **發行轉換規則** ] 索引標籤，並確認已成功建立新的轉換規則。</span><span class="sxs-lookup"><span data-stu-id="518ca-121">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

