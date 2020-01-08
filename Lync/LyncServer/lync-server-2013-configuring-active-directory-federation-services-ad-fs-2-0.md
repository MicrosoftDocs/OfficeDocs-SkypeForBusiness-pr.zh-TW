---
title: Lync Server 2013：設定 Active Directory Federation Services （AD FS 2.0）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a88fb9db7109bdd2a2938f8f9624b4fd0f369fd9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40978223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="4b603-102">正在為 Lync Server 2013 設定 Active Directory Federation Services （AD FS 2.0）</span><span class="sxs-lookup"><span data-stu-id="4b603-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b603-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="4b603-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="4b603-104">下列章節說明如何設定 Active Directory 同盟服務（AD FS 2.0）以支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="4b603-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="4b603-105">如需如何安裝 AD FS 2.0 的詳細資訊，請參閱 AD FS 2.0 逐步說明和操作指南[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。</span><span class="sxs-lookup"><span data-stu-id="4b603-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="4b603-106">安裝 AD FS 2.0 時，請不要使用 Windows Server Manager 來新增 Active Directory 同盟服務角色。</span><span class="sxs-lookup"><span data-stu-id="4b603-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="4b603-107">請改為在上<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>下載並安裝 Active Directory Federation SERVICES 2.0 RTW 套件。</span><span class="sxs-lookup"><span data-stu-id="4b603-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="4b603-108">**針對雙因素驗證設定 AD FS**</span><span class="sxs-lookup"><span data-stu-id="4b603-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="4b603-109">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="4b603-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="4b603-110">啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4b603-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="4b603-111">從 [Windows PowerShell] 命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4b603-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="4b603-112">建立與每個 Lync Server 2013 的合作關係，包括 Lync Server 2013 的累積更新：7月2013主管、Enterprise Pool 及標準版伺服器，只要執行下列命令，就能以備用驗證來取代您的部署專用的伺服器名稱：</span><span class="sxs-lookup"><span data-stu-id="4b603-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="4b603-113">從 [管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="4b603-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="4b603-114">展開 [**信任關聯** \>性**信賴方信任**]。</span><span class="sxs-lookup"><span data-stu-id="4b603-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="4b603-115">確認已為您的 Lync Server 2013 建立新的信任，並累積更新 Lync Server 2013：7月2013企業版池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="4b603-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="4b603-116">若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行授權規則：</span><span class="sxs-lookup"><span data-stu-id="4b603-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="4b603-117">若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行轉換規則：</span><span class="sxs-lookup"><span data-stu-id="4b603-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="4b603-118">從 AD FS 2.0 管理主控台，以滑鼠右鍵按一下您的信賴方信任，然後選取 [**編輯宣告規則**]。</span><span class="sxs-lookup"><span data-stu-id="4b603-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="4b603-119">選取 [**發佈授權規則**] 索引標籤，並確認已成功建立新的授權規則。</span><span class="sxs-lookup"><span data-stu-id="4b603-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="4b603-120">選取 [**頒發轉換規則**] 索引標籤，並確認已成功建立新的轉換規則。</span><span class="sxs-lookup"><span data-stu-id="4b603-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

