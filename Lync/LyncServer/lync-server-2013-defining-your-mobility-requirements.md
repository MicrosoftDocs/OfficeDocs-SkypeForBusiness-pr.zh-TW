---
title: Lync Server 2013：定義行動需求
description: Lync Server 2013：定義行動性需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545539"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>定義 Lync Server 2013 的行動需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在 Lync Server 2013 行動功能的規劃階段期間，當您使用 Lync 2010 行動裝置和 Lync 2013 行動用戶端時，決定您的部署步驟。

以下是您必須考慮的決策：

  - **您是否要使用 Lync mobile 用戶端的自動探索？**
    
    如果您想要支援自動探索，您必須建立新的內部及外部網域名稱系統 (DNS) 記錄、將主體替代名稱新增至前端伺服器、Director 及反向 proxy 上的憑證，以及修改反向 proxy 上的現有發佈規則。 如需詳細資訊，請參閱 [Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。 透過自動探索，使用者可以自動從公司網路內部或外部的任何地方尋找 Lync Server 2013 Web 服務，而不需要在行動裝置設定中輸入 URLs。
    
    如果您使用手動設定，而不是自動探索，行動使用者必須在行動裝置中手動輸入下列 URLs：
    
      - HTTPs:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root 用於外部存取
    
      - HTTPs:// \<IntPoolFQDN\> /AutoDiscover/autodiscoverservice .svc/Root for internal access
    
    強烈建議使用自動探索。 手動設定的主要用途是用於疑難排解。

  - **如果您決定要支援自動探索，是否願意以每個 SIP 網域的主體替代名稱更新反向 proxy 上的憑證？**
    
    如果您有許多 SIP 網域，更新反向 proxy 上的公用憑證會變得非常昂貴。 如果是這種情況，您可以選擇執行自動探索，讓初始自動探索服務要求在埠80上使用 HTTP，而不是在埠443上使用 HTTPS。 不過，這不是建議的方法。 如果您決定選擇此選項，則不需要更新反向 proxy 上的憑證，但是您必須在埠80上建立 HTTP 的 web 發行規則。 如需詳細資訊，請參閱 [Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **您想要在公司網路內部和外部都支援 Lync 行動用戶端，還是只支援公司網路內的用戶端？**
    
    如果您想要在網路內部和外部支援行動用戶端，行動裝置可以從任何位置存取行動功能。 預設設定是支援公司網路的內部及外部用戶端。
    
    雖然預設設定可讓行動用戶端流量透過外部網站，但您可以將行動用戶端流量限制在內部公司網路中。 當您將流量限制為內部網路時，使用者只有在網路內部時，才可以在其行動裝置上使用 Lync 行動應用程式。
    
    針對使用 Mcx 行動性服務和 Lync 2010 Mobile 支援行動的部署，您可以執行 **Set-CsMcxConfiguration** Cmdlet。 若要設定僅限內部使用的行動性，請使用類似下列的命令：
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA 不需要其他設定。 UCWA 沒有同等的僅限內部配置。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您使用的是 Lync Server 2013 &nbsp; 前端伺服器或前端集區，而且 <STRONG>沒有</STRONG> 任何 Lync Server 2010 &nbsp; 前端伺服器或前端集區，則不 <STRONG>需要以 cookie 為基礎的持久性</STRONG>。 如果您需要保留任何 Lync Server 2010 &nbsp; 前端伺服器或前端集區，相同的規則仍會在 Lync Server 2010 中套用，以用於 cookie 型暫留。

    
    </div>

  - **您是否要支援 Apple iOS 裝置和 Windows phone 的推播通知？**
    
    如果您支援推播通知，支援的 Apple iOS 裝置和 Windows phone 會收到當行動應用程式非使用中時發生的事件通知。 您必須設定 Edge Server 才能與雲端式 Lync Server 推播通知服務（位於 Lync Online 資料中心）進行同盟關聯，並執行 Cmdlet 以啟用推播通知。
    
    如果您想要支援 Wi-Fi 網路的推播通知，除了支援行動裝置供應商的3G 或資料網路上的推播通知之外，您必須開啟企業 Wi-Fi 網路上的埠5223輸出。 支援透過 Wi-Fi 網路的推播通知，可支援行動裝置，只使用具有低室內接待的 Wi-Fi 和行動裝置。
    
    <div>
    

    > [!IMPORTANT]  
    > 只有在支援執行 Lync 2010 行動用戶端的 Apple 裝置時，才需要開啟埠 TCP 5223。

    
    </div>
    
    如果不支援推播通知，Apple 行動裝置和 Windows phone 的使用者將不會發現使用中行動應用程式非使用中時所發生的事件（例如立即訊息邀請或錯過的郵件）。
    
    <div>
    

    > [!NOTE]  
    > Apple 裝置上的 Lync 2013 行動用戶端不需要推播通知。 在 Windows Phone 上的 Lync 2013 行動用戶端會使用推播通知。 規劃推播通知及推播通知的情況，在 Windows Phone 和 Apple 裝置上的 Lync Mobile 會保持不變，但無法執行 Lync 2013 行動用戶端。

    
    </div>

  - **您是否要讓所有使用者都能存取行動功能，或是否要能夠指定哪些使用者可以存取這些功能？**
    
    該表說明 Lync Server 2013 中使用者可用的功能。 預設值允許透過工作撥打，允許 VoIP) 的語音 over IP (，並啟用行動性。 以下是可用選項的完整集合：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>功能/參數名稱/範圍 (原則參數名稱可能不同) </th>
    <th>描述</th>
    <th>已導入</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>啟用行動性</p>
    <p>參數名稱： <code>EnableMobility</code></p>
    <p>範圍： Global/Site/User</p></td>
    <td><p>管理設定若要控制已安裝 Lync Mobile 之指定範圍內的使用者，如果原則設定為 False，使用者就無法登入用戶端。</p>
    <p>預設設定為 True。</p></td>
    <td><p>Lync Server 2010 的累計更新：11月2011</p></td>
    </tr>
    <tr class="even">
    <td><p>啟用外語音</p>
    <p>參數名稱： <code>EnableOutsideVoice</code></p>
    <p>範圍： Global/Site/User</p></td>
    <td><p>控制使用者使用「呼叫者」功能的能力，該功能可讓使用者使用其公司電話號碼，而不是其行動電話號碼，撥打和接聽電話。 若設為 False，使用者將無法使用其行動裝置撥打或接聽其公司電話號碼。</p>
    <p>預設設定為 True</p></td>
    <td><p>Lync Server 2010 的累計更新：11月2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>啟用 IP 音訊和影片</p>
    <p>參數名稱： <code>EnableIPAudioVideo</code></p>
    <p>範圍： Global/Site/User</p></td>
    <td><p>控制使用者是否可以使用 VoIP 在其行動裝置上撥打或接聽語音或視頻通話。 如果設為 False，使用者將無法在其裝置上撥打或接收 VoIP 或視頻通話。</p>
    <p>預設設定為 True。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>需要 IP 音訊的 WiFi</p>
    <p>參數名稱： <code>RequireWiFiForIPAudio</code></p>
    <p>範圍： Global/Site/User</p></td>
    <td><p>此設定定義用戶端是否需要在 WiFi 上的 VoIP 上撥打和接聽電話，而不是行動電話資料網路。 如果設為 True，使用者只有在連線至 WiFi 網路時，才能撥打和接收 VoIP 呼叫。</p>
    <p>預設設定為 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>需要 IP 影片的 WiFi</p>
    <p>參數名稱： <code>RequireWiFiForIPVideo</code></p>
    <p>範圍： Global/Site/User</p></td>
    <td><p>此設定定義是否需要用戶端在 Wi-Fi，而不是在行動電話資料網路上撥打和接收通話。 如果設為 True，使用者只有在連線至 Wi-Fi 網路時，才能撥打及接收影片通話。</p>
    <p>預設設定為 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    如需您可以設定之原則設定的描述，以及如何管理原則，請參閱 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 及 [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。

  - **您是否要讓未啟用 Enterprise Voice 的使用者能夠使用按一下以加入加入會議？**
    
    若要讓使用者能夠存取行動功能及呼叫透過工作，必須啟用 Enterprise Voice。 不過，未啟用 Enterprise Voice 的使用者可以按一下其行動裝置上的連結，以加入會議，如果他們具有適當的語音原則給他們。 您可以將特定的語音原則指派給這些使用者，或確定存在套用至這些使用者的全域原則或網站層級原則。 您指派的語音原則必須具有公用交換電話網路 (PSTN) 使用方式記錄和路由，以定義使用者可以撥出的區域，以加入會議。 如需有關設定語音原則、PSTN 使用方式記錄和路由的詳細資訊，請參閱 [在 Lync Server 2013 中設定語音原則、pstn 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。
    
    <div>
    

    > [!NOTE]  
    > 想要使用 [按一下以加入] 的行動使用者需要語音原則，以及相關的 PSTN 使用方式記錄和語音路由，因為按一下行動裝置上的連結會產生來自 Lync Server 2013 的撥出電話。

    
    </div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)  


[在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

