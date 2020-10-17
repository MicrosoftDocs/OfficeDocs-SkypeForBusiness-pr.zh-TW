---
title: 'Lync Server 2013：設定 Active Directory Federation Services (AD FS 2.0) '
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
ms.openlocfilehash: ac26f7ec2be8390ee913c810928cc99c4e20d53c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517650"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>為 Lync Server 2013 設定 Active Directory Federation Services (AD FS 2.0) 

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

下列章節說明如何設定 Active Directory Federation Services (AD FS 2.0) 以支援多重要素驗證。 如需如何安裝 AD FS 2.0 的詳細資訊，請參閱《 AD FS 2.0 逐步逐步說明》 [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) 。

<div class="">


> [!NOTE]  
> 安裝 AD FS 2.0 時，請勿使用 Windows Server 管理員來新增 Active Directory Federation Services 角色。 請改為在上下載並安裝 Active Directory Federation Services 2.0 幫手 RTW 套件 <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> 。



</div>

<div>


**設定用於雙因素驗證的 AD FS**

1.  使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2.  啟動 Windows PowerShell。

3.  在 [Windows PowerShell] 命令列中，執行下列命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  使用 Lync Server 2013 的累計更新，建立與每個 Lync Server 2013 的合作關係：7月 2013 Director、Enterprise Pool 和 Standard Edition Server，可執行下列命令取代專用於您的部署的伺服器名稱，以供啟用被動驗證：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  在 [系統管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。

6.  展開 [ **信任關係** \> **信賴**憑證者信任]。

7.  請確認已為您的 Lync Server 2013 建立新的信任，其具有 Lync Server 2013 的累計更新：7月 2013 Enterprise Pool 或 Standard Edition Server。

8.  執行下列命令，為使用 Windows PowerShell 的信賴憑證者信任建立並指派發行授權規則：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  執行下列命令，為您使用 Windows PowerShell 建立並指派「信賴憑證方信任」的發行轉換規則：
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. 在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下您的信賴憑證者信任，然後選取 [ **編輯宣告規則**]。

11. 選取 [ **發行授權規則** ] 索引標籤，並確認已成功建立新的授權規則。

12. 選取 [ **發行轉換規則** ] 索引標籤，並確認已成功建立新的轉換規則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

