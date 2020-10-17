---
title: Lync Server 2013：將 Lync Online 使用者遷移至 Lync 內部部署
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
ms.openlocfilehash: 8a2be7414dbdc48c9e245db33e57b8238cfb2ee9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520990"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>將 Lync Online 使用者遷移至 lync Server 2013 中的 Lync 內部部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 在您部署 Lync 內部部署之前，只需要將已在 Lync Online 中啟用 Lync 的使用者帳戶遷移時，才需要執行這些步驟。 若要將原來啟用 Lync 內部部署的使用者移動，之後移至 Lync Online，請參閱 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理使用者</A>。<BR>此外，所有移動的使用者都必須擁有內部部署 Active Directory 中的帳戶。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>將 Lync Online 中原來啟用的使用者帳戶遷移至 Lync On-Premises

1.  首先，請確定您的組織已設定成混合式。
    
      - 安裝 Azure Active Directory 同步作業工具。 如需詳細資訊，請參閱 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。
    
      - 若要讓您的使用者可以使用單一登入來進行 Lync Online，請安裝 Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 。
    
      - 在您的內部部署中，在 Lync Server 管理命令介面中輸入下列 Cmdlet，以建立 Lync Online 的裝載提供者：
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  請確認，在您的內部部署 Edge Server 上，您的憑證鏈可以啟用與 Lync Online 的連線，如下表所示。 您可以在這裡下載此連結： https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>認證</th>
    <th>憑證儲存區</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>受信任的根 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet 核證機關 (新 CA 憑證) </p></td>
    <td><p>中間 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT)  (新發出 CA2 的機器驗證 CA2</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  在您的內部部署 Active Directory 中，針對 Lync 內部部署啟用受影響的使用者帳戶。 您可以輸入下列 Cmdlet，為個別使用者執行這項操作：
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    或者，您也可以建立從檔案讀取使用者名稱的腳本，並將其提供給 Enable-CsUser Cmdlet 的輸入：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  執行 DirSync，以同步處理 Lync Online 使用者與更新的 Lync 內部部署使用者。

5.  更新一些 DNS 記錄，以將所有 SIP 流量定向至 Lync 內部部署：
    
      - 更新 **Lyncdiscover.contoso.com** A 記錄，使其指向內部部署反向 proxy 伺服器的 FQDN。
    
      - 更新 *** \_ sip *。 \_tls.contoso.com** SRV 記錄，以解析至 Lync 內部部署的 Access Edge service 的公用 IP 或 VIP 位址。
    
      - 更新 *** \_ sipfederationtls *。 \_tcp.contoso.com** SRV 記錄，以解析至 Lync 內部部署的 Access Edge service 的公用 IP 或 VIP 位址。
    
      - 如果您的組織使用的分割 DNS (有時稱為「分裂-大腦 DNS」 ) ，請確定透過內部 DNS 區域解析名稱的使用者會定向至前端集區。

6.  輸入 `Get-CsUser` Cmdlet 以檢查您將會移動之使用者的一些屬性。 您想確定 HostingProviderProxyFQDN 已設定為 `"sipfed.online.lync.com"` ，且 SIP 位址設定正確。

7.  將 Lync Online 使用者移至 Lync 內部部署。
    
    若要移動單一使用者，請輸入：
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    您可以使用 **get-csuser** 指令程式和– Filter 參數來移動多位使用者，以選取具有特定屬性的使用者。 例如，您可以透過篩選 {主控提供者– eq "sipfed.online.lync.om"} 來選取所有的 Lync Online 使用者。 然後，您可以將傳回的使用者輸送至 **get-csuser** Cmdlet，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    針對 **HostedMigrationOverrideUrl** 參數所指定的 url 格式，必須是正在執行裝載遷移服務之集區的 url，格式如下： *Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*。
    
    您可以透過查看 Microsoft 365 或 Office 365 組織帳戶的 Lync Online 控制台 URL，來決定主控遷移服務的 URL。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>決定 organizaton 的主控遷移服務 URL
    
    1.  以管理員身分登入您的 Microsoft 365 或 Office 365 組織。
    
    2.  開啟 **Lync 系統管理中心**。
    
    3.  在 [ **Lync 系統管理中心** ] 顯示時，選取 [位址] 列中的 URL，並將其複製到 **lync.com**。 URL 的範例類似下列所示：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  使用系統**管理員**取代 URL 中的**webdir** ，產生下列結果：
        
        `https://admin0a.online.lync.com`
    
    5.  在 URL: **/HostedMigration/hostedmigrationservice.svc**中附加下列字串。
        
        產生的 URL （ **HostedMigrationOverrideUrl**的值）應如下所示：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds 資料庫之交易記錄檔的預設大小上限為 16 GB。 如果您同時移動大量的使用者，尤其是當您已啟用鏡像，這樣做可能會不夠大。 若要解決此問題，您可以定期增加檔案大小或備份記錄檔。 如需詳細資訊，請參閱 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。

    
    </div>

8.  這是選擇性的步驟。 如果您需要與 Exchange 2013 線上整合，您必須使用其他主機服務提供者。 如需詳細資訊，請參閱設定 [內部部署 Lync Server 2013 與 Exchange Online 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

9.  現在已移動使用者。 若要檢查使用者在下表中顯示的屬性是否具有正確的值，請輸入此 Cmdlet：
    
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
    <th>正確的 Lync Online 使用者值</th>
    <th>正確的 Lync 使用者-內部部署使用者值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>DNS-SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>啟用</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 已移動的每個使用者都必須登入 Lync，然後重新登入。 當他們登入時，應驗證他們的連絡人清單，並視需要新增連絡人。
    
    請注意，排定的會議不會從 Lync Online 遷移至 Lync 內部部署。 使用者在移動這些會議之後，將需要重新排定。
    
    在更新 DNS 記錄，並將所有使用者定向至內部部署後，HostingProvider 屬性會指示 Lync 使用者使用 SRV 記錄，或將其指引至線上提供者 "sipfed.online.lync.com"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

