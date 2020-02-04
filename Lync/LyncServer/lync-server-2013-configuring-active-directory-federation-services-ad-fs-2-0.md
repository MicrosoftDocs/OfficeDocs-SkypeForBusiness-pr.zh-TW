---
title: Lync Server 2013：設定 Active Directory Federation Services （AD FS 2.0）
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
ms.openlocfilehash: 68864b6e5773bcd1cb9f063b400015697285ba36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>正在為 Lync Server 2013 設定 Active Directory Federation Services （AD FS 2.0）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

下列章節說明如何設定 Active Directory 同盟服務（AD FS 2.0）以支援多重要素驗證。 如需如何安裝 AD FS 2.0 的詳細資訊，請參閱 AD FS 2.0 逐步說明和操作指南[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。

<div class="">


> [!NOTE]  
> 安裝 AD FS 2.0 時，請不要使用 Windows Server Manager 來新增 Active Directory 同盟服務角色。 請改為在上<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>下載並安裝 Active Directory Federation SERVICES 2.0 RTW 套件。



</div>

<div>


**針對雙因素驗證設定 AD FS**

1.  使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2.  啟動 Windows PowerShell。

3.  從 [Windows PowerShell] 命令列中，執行下列命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  建立與每個 Lync Server 2013 的合作關係，包括 Lync Server 2013 的累積更新：7月2013主管、Enterprise Pool 及標準版伺服器，只要執行下列命令，就能以備用驗證來取代您的部署專用的伺服器名稱：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  從 [管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。

6.  展開 [**信任關聯** \>性**信賴方信任**]。

7.  確認已為您的 Lync Server 2013 建立新的信任，並累積更新 Lync Server 2013：7月2013企業版池或標準版伺服器。

8.  若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行授權規則：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行轉換規則：
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. 從 AD FS 2.0 管理主控台，以滑鼠右鍵按一下您的信賴方信任，然後選取 [**編輯宣告規則**]。

11. 選取 [**發佈授權規則**] 索引標籤，並確認已成功建立新的授權規則。

12. 選取 [**頒發轉換規則**] 索引標籤，並確認已成功建立新的轉換規則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

