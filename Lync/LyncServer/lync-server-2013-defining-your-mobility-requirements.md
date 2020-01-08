---
title: Lync Server 2013：定義行動需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>定義 Lync Server 2013 的行動需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在 Lync Server 2013 行動裝置的規劃階段，當您使用 Lync 2010 Mobile 和 Lync 2013 行動用戶端時，決定您的部署步驟。

以下是您必須考慮的決定：

  - **您想要使用 Lync mobile 用戶端的自動探索嗎？**
    
    如果您想要支援自動探索，您需要建立新的內部和外部網域名稱系統（DNS）記錄，在前端伺服器、控制器和反向 proxy 上將 subject 備用名稱新增至憑證，以及修改現有的發佈規則在反向 proxy 上。 如需詳細資訊，請參閱[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。 透過自動搜尋，使用者可以自動找到公司網路內部或外部的 Lync Server 2013 Web 服務，而不需在行動裝置設定中輸入 Url。
    
    如果您使用手動設定，而不是自動探索，行動使用者必須在行動裝置上手動輸入下列 Url：
    
      - HTTPs://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 以進行外部存取
    
      - HTTPs://\<IntPoolFQDN\>/AutoDiscover/autodiscoverservice-內部存取的 .svc/Root
    
    我們強烈建議您使用自動探索。 手動設定的主要用途是為了進行疑難排解。

  - **如果您決定要支援自動探索，您是否願意使用每個 SIP 網域的消費者備用名稱來更新反向 proxy 上的憑證？**
    
    如果您有許多 SIP 網域，更新反向 proxy 上的公用憑證會變得非常昂貴。 如果是這種情況，您可以選擇實施自動探索，讓初始自動探索服務要求在埠80上使用 HTTP，而不是在埠443上使用 HTTPS。 不過，這不是建議的方法。 如果您決定選擇此選項，則不需要更新反向 proxy 上的憑證，但是您需要在埠80上建立 HTTP 的 web 發佈規則。 如需詳細資訊，請參閱[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **您想要支援在公司網路內部和外部的 Lync 行動用戶端，或只支援公司網路內的用戶端嗎？**
    
    如果您想要在您的網路內部和外部支援行動用戶端，行動裝置就能從任何位置存取行動裝置功能。 預設設定是支援公司網路內部和外部的用戶端。
    
    雖然預設設定可讓行動用戶端流量透過外部網站進行，但是您可以將行動用戶端流量限制在內部公司網路。 當您將流量限制在內部網路時，使用者只能在他們的行動裝置上使用 Lync 行動應用程式（只有在網路內）。
    
    針對使用 Mcx 行動服務和 Lync 2010 Mobile 支援行動裝置的部署，您可以執行**CsMcxConfiguration** Cmdlet。 若要設定行動僅供內部使用，您可以使用類似以下的命令：
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA 不需要其他設定。 UCWA 沒有同等的內部專用配置。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您使用的是 Lync Server 2013&nbsp;前端伺服器或前端池，且<STRONG>您沒有</STRONG>任何 Lync server 2010&nbsp;前端伺服器或前端池，就不需要<STRONG>以 cookie 為基礎的持久性</STRONG>。 如果您需要保留任何 Lync Server 2010&nbsp;前端伺服器或前端池，相同的規則仍然會在 Lync Server 2010 中與針對 cookie 的持久性一起使用。

    
    </div>

  - **您想要支援 Apple iOS 裝置和 Windows phone 的推播通知嗎？**
    
    如果您支援推播通知，支援的 Apple iOS 裝置和 Windows phone 收到行動應用程式停用時所發生事件的通知。 您必須將 Edge 伺服器設定為與雲端的 Lync Server 推播通知服務（位於 Lync Online 資料中心），並執行 Cmdlet 來啟用推播通知。
    
    如果您想要在您的 Wi-fi 網路上支援推播通知，除了支援行動裝置提供者或資料網路上的推播通知之外，您必須先在企業版 Wi-fi 網路上開啟埠5223輸出。 在 Wi-fi 網路上支援推播通知支援行動裝置，只使用 Wi-fi，且室內接收不佳的行動裝置。
    
    <div>
    

    > [!IMPORTANT]  
    > 只有在支援執行 Lync 2010 行動用戶端的 Apple 裝置時，才需要開啟埠 TCP 5223。

    
    </div>
    
    如果您不支援推播通知，Apple 行動裝置和 Windows phone 的使用者將無法瞭解行動應用程式停用時所發生的事件（例如立即訊息邀請或未接的訊息）。
    
    <div>
    

    > [!NOTE]  
    > Apple 裝置上的 Lync 2013 行動用戶端不需要推播通知。 Windows Phone 上的 Lync 2013 行動用戶端會使用推播通知。 規劃推播通知和推播通知 clearinghouse 在 Windows Phone 上的 Lync Mobile 與不能執行 Lync 2013 行動用戶端的 Apple 裝置上保持不變。

    
    </div>

  - **您是否要讓所有使用者都能存取行動功能，或者您想要能夠指定哪些使用者可以存取這些功能嗎？**
    
    下表說明 Lync Server 2013 中使用者可用的功能。 預設值允許透過工作撥打電話、允許語音使用 IP （VoIP），以及啟用行動性。 以下是可用選項的完整集合：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>功能/參數名稱/範圍（原則參數名稱可能不一樣）</th>
    <th>描述</th>
    <th>採用</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>啟用行動性</p>
    <p>參數名稱：<code>EnableMobility</code></p>
    <p>範圍：全域/網站/使用者</p></td>
    <td><p>在已安裝 Lync Mobile 的指定範圍內控制使用者的系統管理設定，如果原則設定為 False，則使用者將無法登入用戶端。</p>
    <p>預設設定為 True。</p></td>
    <td><p>Lync Server 2010 的累積更新：2011年11月</p></td>
    </tr>
    <tr class="even">
    <td><p>啟用外部語音</p>
    <p>參數名稱：<code>EnableOutsideVoice</code></p>
    <p>範圍：全域/網站/使用者</p></td>
    <td><p>控制使用者在工作中使用通話的能力，這項功能可讓使用者使用其公司電話撥打及接聽電話，而不是行動電話號碼。 如果設定為 False，使用者將無法使用其行動裝置上的公司電話號碼撥打或接聽電話。</p>
    <p>預設設定為 True</p></td>
    <td><p>Lync Server 2010 的累積更新：2011年11月</p></td>
    </tr>
    <tr class="odd">
    <td><p>啟用 IP 音訊和影片</p>
    <p>參數名稱：<code>EnableIPAudioVideo</code></p>
    <p>範圍：全域/網站/使用者</p></td>
    <td><p>控制使用者是否可以在行動裝置上使用 VoIP 撥打或接聽語音或視頻通話。 如果設定為 False，使用者將無法在其裝置上撥打或接聽 VoIP 或視頻通話。</p>
    <p>預設設定為 True。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>需要 IP 音訊的 WiFi</p>
    <p>參數名稱：<code>RequireWiFiForIPAudio</code></p>
    <p>範圍：全域/網站/使用者</p></td>
    <td><p>此設定會定義用戶端是否需要在網路上使用 VoIP 來撥打和接聽 VoIP，而非行動資料網路。 如果設定為 True，則使用者只能在連線到 WiFi 網路時撥打和接聽 VoIP 通話。</p>
    <p>預設設定為 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 視頻需要 WiFi</p>
    <p>參數名稱：<code>RequireWiFiForIPVideo</code></p>
    <p>範圍：全域/網站/使用者</p></td>
    <td><p>此設定會定義用戶端是否需要在 Wi-fi 上撥打和接聽視頻通話，而不是在行動資料網路上。 如果設為 True，則使用者只能在連線到 Wi-fi 網路時撥打及接聽視頻通話。</p>
    <p>預設設定為 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    如需您可以設定之原則設定的描述，以及如何管理原則，請參閱[新-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)及[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。

  - **您是否要讓未啟用企業語音的使用者可以使用「按一下」加入加入會議？**
    
    若要讓使用者能夠存取行動功能，以及透過公司通話，必須為企業語音啟用這些功能。 不過，如果使用者未啟用企業語音，您可以按一下行動裝置上的連結來加入會議（如果他們已獲指派適當的語音原則）。 您可以將特定的語音原則指派給這些使用者，或是確定其適用的是全域原則或網站層級原則。 您指派的語音原則必須具有公用交換電話網絡（PSTN）使用記錄及路由，以定義使用者可以撥出以加入會議的區域。 如需有關設定語音原則、PSTN 使用方式記錄及路由的詳細資料，請參閱[在 Lync Server 2013 中設定語音原則、pstn 使用方式記錄及語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。
    
    <div>
    

    > [!NOTE]  
    > 想要使用 [按一下以加入] 的行動使用者，以及相關的 PSTN 使用記錄和語音路由，因為按一下行動裝置上的連結會產生 Lync Server 2013 的出站通話。

    
    </div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)  


[在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

