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
ms.openlocfilehash: e76f8c0c40e13d0d9c6b19dee118e1513390d7e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>將 Lync Online 使用者遷移至 Lync Server 2013 中的 Lync 內部部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 只有在您部署 Lync 內部部署之前，才能在 Lync Online 中將原先啟用 Lync 的使用者帳戶遷移時，才需要執行下列步驟。 若要移動最初啟用 Lync 內部部署的使用者，然後再移至 Lync Online，請參閱<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合式 Lync Server 2013 部署中管理使用者</A>。<BR>此外，移動的所有使用者都必須在內部部署的 Active Directory 中擁有帳戶。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>將已在 Lync Online 中最初啟用的使用者帳戶遷移至 Lync 內部部署

1.  首先，請確定您的組織已設定為混合式。
    
      - 安裝 Azure Active Directory 同步處理工具。 如需詳細資訊， <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>請參閱。
    
      - 若要讓您的使用者能夠使用單一登入進行 Lync Online，請安裝 Active Directory Federation <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>Services。
    
      - 在您的內部部署中，于 Lync Server 管理命令介面輸入下列 Cmdlet，以建立 Lync Online 的主機服務提供者：
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  確認在您的內部部署邊緣伺服器上，您有可連線至 Lync Online 的憑證鏈，如下表所示。 您可以在這裡下載此連結：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>憑證</th>
    <th>證書存放區</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>巴爾的摩 CyberTrust 根</p></td>
    <td><p>受信任的根 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft 網際網路頒發機構（新的 CA 憑證）</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT 電腦驗證 CA2 （新發行 CA2）</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  在您的內部部署 Active Directory 中，針對 Lync 內部部署啟用受影響的使用者帳戶。 您可以輸入下列 Cmdlet 來為個別使用者執行此動作：
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    或者，您可以建立一個腳本來讀取檔案中的使用者名稱，並將其提供給 Enable-Move-csuser Cmdlet 的輸入：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  執行 DirSync 以同步處理 Lync Online 使用者與更新的 Lync 內部部署使用者。

5.  更新部分 DNS 記錄，將所有 SIP 流量引導至 Lync 內部部署：
    
      - 更新**Lyncdiscover.contoso.com** A 記錄，以指向內部部署反向 proxy 伺服器的 FQDN。
    
      - 更新 ***\_sip *。\_tls.contoso.com** SRV 記錄，以解析為 Lync 內部部署之存取邊緣服務的公用 IP 或 VIP 位址。
    
      - 更新 ***\_sipfederationtls *。\_tcp.contoso.com** SRV 記錄，以解析為 Lync 內部部署之存取邊緣服務的公用 IP 或 VIP 位址。
    
      - 如果您的組織使用的是剝離 DNS （有時稱為「分割大腦 DNS」），請確認透過內部 DNS 區域解析名稱的使用者會被導向到前端池。

6.  輸入`Get-CsUser` Cmdlet，以檢查您將移動之使用者的一些屬性。 您想要確認 HostingProviderProxyFQDN 已設定為`"sipfed.online.lync.com"` ，且正確地設定了 SIP 位址。

7.  將 Lync Online 使用者移至 Lync 內部部署。
    
    若要移動單一使用者，請輸入：
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    您可以使用**move-csuser** Cmdlet 和– Filter 參數來移動多個使用者，以選取具有特定屬性的使用者。 例如，您可以透過篩選 {主機服務提供者-eq "sipfed.online.lync.om"} 來選取所有 Lync Online 使用者。 然後，您可以將傳回的使用者輸送至**move-csuser** Cmdlet，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    針對**HostedMigrationOverrideUrl**參數所指定的 url 格式，必須是正在執行託管遷移服務之池的 url，格式如下： *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc*。
    
    您可以透過查看 Office 365 租使用者帳戶的 Lync Online 控制台 URL 來判斷託管遷移服務的 URL。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>若要為您的 Office 365 租使用者判斷託管的遷移服務 URL
    
    1.  以系統管理員身分登入您的 Office 365 租使用者。
    
    2.  開啟**Lync 系統管理中心**。
    
    3.  在**Lync 系統管理中心**顯示的狀態下，選取並將網址列中的 URL 複製到**lync.com**。 範例 URL 看起來類似以下所示：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  將 URL 中的**webdir 為 admin**取代為系統**管理員**，並產生下列結果：
        
        `https://admin0a.online.lync.com`
    
    5.  將下列字串附加到 URL： **/HostedMigration/hostedmigrationservice.svc**。
        
        產生的 URL （即**HostedMigrationOverrideUrl**的值）應如下所示：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds 資料庫之事務記錄日誌檔案的預設最大大小為 16 GB。 如果您要一次移動大量的使用者，尤其是在已啟用鏡像的情況下，這可能不會足夠大。 若要解決此情況，您可以定期增加檔案大小，或定期備份記錄檔案。 如需詳細資訊， <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>請參閱。

    
    </div>

8.  此為選用步驟。 如果您需要在線上與 Exchange 2013 整合，您需要使用其他主機服務提供者。 如需詳細資訊，請參閱設定[內部部署 Lync Server 2013 與 Exchange Online 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

9.  現在已移動使用者。 若要檢查使用者是否具有下表所示屬性的正確值，請輸入以下 Cmdlet：
    
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
    <th>Lync Online 使用者的正確值</th>
    <th>Lync 內部部署使用者的正確值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
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
    <td><p>後</p></td>
    <td><p>滿足</p></td>
    <td><p>滿足</p></td>
    </tr>
    </tbody>
    </table>


10. 已移動的每位使用者都會需要登出 Lync，然後再重新登入。 當他們登入時，請確認他們的連絡人清單，並視需要新增連絡人。
    
    請注意，排程的會議不會從 Lync Online 遷移至 Lync 內部部署。 在移動之後，使用者將需要重新排程這些會議。
    
    在 DNS 記錄經過更新，且所有使用者都被導向到內部部署之後，HostingProvider 屬性會指引 Lync 使用者使用 SRV 記錄，或將其引導至線上提供者「sipfed.online.lync.com」。

</div>

</div>

<span> </span>

</div>

</div>

</div>

