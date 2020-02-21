---
title: Lync Server 2013： 移轉至 Lync 內部部署的 Lync Online 使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f10aedf2a183e7ad965ba36ea0610fc02b93dfce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Lync Online 移轉至 Lync 內部使用者在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015 年 11 月 13 日_

<div class="">


> [!IMPORTANT]  
> 下列步驟所需僅適用於移轉已在才能 Lync 內部部署原本 Lync Online 中的 lync 啟用的使用者帳戶。 移動使用者原本已啟用 Lync 內部部署，然後稍後會移至 Lync Online，請參閱<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md"> Administering 使用者在混合式架構 Lync Server 2013 部署</A>。<BR>此外，要移動的所有使用者必須都擁有內部部署 Active Directory 中的帳戶。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>原本要 Lync 內部部署啟用 Lync Online 中的遷移使用者帳戶

1.  首先，請確定您的組織已針對混合式。
    
      - 安裝 Azure Active Directory 同步作業工具。 如需詳細資訊，請參閱 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。
    
      - 若要啟用您的使用者可使用單一登入 Lync Online，請安裝 Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>。
    
      - 在內部部署 Lync Server 管理命令介面中輸入下列 cmdlet 來建立對 Lync Online 的裝載提供者：
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  確認，您的內部 Edge 伺服器上，您具有可讓連線到 Lync Online、 憑證鏈結，如下表所示。 您可以下載這個鏈結這裡：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>認證</th>
    <th>憑證存放區</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>受信任的根 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet 授權單位 （新增 CA 憑證）</p></td>
    <td><p>中繼 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT 機器驗證 CA2 （新發行 CA2）</p></td>
    <td><p>中繼 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  在您的內部部署 Active Directory，以啟用 Lync 內部部署的受影響的使用者帳戶。 您可以這麼做為個別使用者輸入下列 cmdlet:
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    或者，您可以建立指令碼，可讀取使用者從檔案名稱，並提供其做為啟用 Get-csuser cmdlet 的輸出：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  執行 DirSync 同步處理與更新的 Lync 內部部署使用者的 Lync Online 使用者。

5.  更新部分的 DNS 記錄，以直接到 Lync 內部部署的所有 SIP 流量：
    
      - 更新**lyncdiscover.contoso.com** A 記錄以指向內部部署反向 proxy 伺服器的 FQDN。
    
      - 更新 ***\_sip *。\_tls.contoso.com** SRV 記錄，以解析為 Lync 內部部署的 Access Edge 服務公用 IP 或 VIP 位址。
    
      - 更新 ***\_sipfederationtls *。\_tcp.contoso.com** SRV 記錄，以解析為 Lync 內部部署的 Access Edge 服務公用 IP 或 VIP 位址。
    
      - 如果您的組織會使用分割 DNS （有時稱為 「 split-brain DNS >），請確定使用者解析透過內部 DNS 區域的名稱會被導向到前端集區。

6.  型別`Get-CsUser`指令程式以檢查您要移動的使用者相關的某些屬性。 您想要確定 HostingProviderProxyFQDN 設為`"sipfed.online.lync.com"`和的 SIP 位址已正確設定。

7.  將 Lync Online 的使用者移至 Lync 內部部署。
    
    若要移動單一使用者，請輸入如下：
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    您可以移動多位使用者使用**Get-csuser** cmdlet 搭配 – Filter 參數來選取特定的屬性與使用者。 例如，您無法選取所有 Lync Online 使用者篩選 {裝載提供者 – eq"sipfed.online.lync.om"}。 您可以再管道**Move-csuser** cmdlet 時，傳回的使用者，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    指定**HostedMigrationOverrideUrl**參數必須是主控遷移服務執行，以下列格式的集區的 URL 的 url 格式： *Https://\<集區 FQDN\>/HostedMigration/hostedmigrationService.svc*。
    
    您可以透過檢視 URL 的 Office 365 租用戶帳戶的 Lync Online 控制台判斷主控移轉服務的 URL。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>若要判斷您 Office 365 租用戶主控移轉服務 URL
    
    1.  Office 365 租用戶系統管理員身分登入。
    
    2.  開啟**Lync 系統管理中心**]。
    
    3.  顯示在**Lync 系統管理中心**，選取與複製最**lync.com**[網址] 列中的 URL。 範例 URL 看起來如下：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  **Webdir** URL 中取代為**系統管理員**，結果如下：
        
        `https://admin0a.online.lync.com`
    
    5.  將下列字串附加至的 URL: **/HostedMigration/hostedmigrationservice.svc**。
        
        產生的 URL，也就是**HostedMigrationOverrideUrl**的值，應該如下所示：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > 預設的 rtcxds 資料庫的交易記錄檔的大小上限為 16 GB。 這可能無法夠大如果您要移動大量的使用者，同時，尤其是如果您有鏡像啟用。 若要解決這個您可以增加檔案大小，或定期備份記錄檔。 如需詳細資訊，請參閱<A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>。

    
    </div>

8.  這是選擇性的步驟。 如果您要與 Exchange 2013 Online 整合，您需要使用其他的主機服務提供者。 如需詳細資訊，請參閱[設定內部部署與 Exchange Online 的 Lync Server 2013 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

9.  使用者現在移。 若要檢查使用者有正確的值，如下表所示的屬性，請輸入此 cmdlet:
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Active Directory 屬性</th>
    <th>屬性名稱</th>
    <th>Lync Online 使用者正確的值</th>
    <th>正確的值為 Lync – 內部使用者的</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>包含 DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com></p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>包含 PrimaryUserAddress</p></td>
    <td><p>則</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>包含 UserEnabled</p></td>
    <td><p>Enabled</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 已移動的每個使用者需要登出 Lync，然後再重新登入。 當他們登入他們應該確認他們的連絡人清單，並視中新增連絡人。
    
    請注意到 Lync 內部未從 Lync Online 移轉排程的會議。 使用者必須重新排程這些會議之後要移動。
    
    HostingProvider 屬性不會更新 DNS 記錄，且所有使用者都導向至內部之後，會指示 Lync 使用者使用 SRV 記錄，或指向線上提供者 」 sipfed.online.lync.com。 」

</div>

</div>

<span> </span>

</div>

</div>

</div>

