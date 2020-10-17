---
title: Lync Server 2013：修改 SIP 主幹設定設定
description: Lync Server 2013：修改 SIP 主幹設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562139"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改 SIP 主幹設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

  - 主幹是否啟用媒體旁路。

  - 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。

  - 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。 您可以稍後使用 Lync Server 控制台或 Windows PowerShell 修改這些集合中的任何集合。

使用 Lync Server 控制台修改 SIP 主幹設定設定時，您可以使用下列選項：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell 參數</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>身分識別</p></td>
<td><p>集合的唯一識別碼。此為唯讀屬性，您無法變更主幹組態設定集合的 Identity。</p></td>
</tr>
<tr class="even">
<td><p>描述</p></td>
<td><p>描述</p></td>
<td><p>為系統管理員提供儲存設定相關資訊 (例如，主幹組態的用途) 的方法。</p></td>
</tr>
<tr class="odd">
<td><p>支援的最大早期對話</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>服務提供者的 PSTN 閘道、IP-PBX 或 SBC 對其傳送到中繼伺服器的 Invite，可接收的分支回應數上限。</p></td>
</tr>
<tr class="even">
<td><p>加密支援等級</p></td>
<td><p>SRTPMode</p></td>
<td><p>指出支援等級，以保護中繼伺服器和服務提供者之 PSTN 閘道、IP-PBX 或 SBC 之間的媒體流量。 若是媒體旁路的情況，此值必須與媒體組態中的 EncryptionLevel 設定相容。 媒體設定是使用 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">新的-CsMediaConfiguration</a> 及 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> Cmdlet 來設定。</p>
<p>允許的值為：</p>
<ul>
<li><p>Required：必須使用 SRTP 加密。</p></li>
<li><p>Optional：如果閘道支援，即會使用 SRTP。</p></li>
<li><p>Not Supported：不支援 SRTP 加密，因此不會使用此加密。</p></li>
</ul>
<p>只有閘道設定為使用傳輸層安全性 (TLS) 時，才能使用 SRTPMode。如果將閘道設定為在傳輸時使用傳輸控制通訊協定 (TCP)，系統會從內部將 SRTPMode 設為 Not Supported。</p></td>
</tr>
<tr class="odd">
<td><p>轉接支援</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>如果設定為 <strong>[啟用傳送轉接至閘道]</strong>，表示主幹支援接收來自中繼伺服器的 Refer 要求。</p>
<p>如果設定為 <strong>[使用協力廠商撥號控制來啟用轉接]</strong>，表示可以使用 3pcc 通訊協定允許轉接通話略過主控網站。 3pcc 也稱為 &quot; 協力廠商控制項， &quot; 當協力廠商用來連接一 (對來電者時，就會發生此事件。例如，操作員撥打某人 a 至 B 的來電) 。</p></td>
</tr>
<tr class="even">
<td><p>啟用媒體旁路</p></td>
<td><p>EnableBypass</p></td>
<td><p>表示此主幹是否啟用媒體旁路。只有在也啟用 <strong>[集中式媒體處理]</strong> 時，才能啟用媒體旁路。</p></td>
</tr>
<tr class="odd">
<td><p>集中式媒體處理</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>指出是否有已知的媒體終端點 (已知的媒體終端點範例是 PSTN 閘道，其媒體終端的 IP 與訊號終端相同)。</p></td>
</tr>
<tr class="even">
<td><p>啟用 RTP 栓</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>指出 SIP 主幹是否支援 RTP 栓。RTP 栓是一種技術，可讓 RTP/RTCP 透過 NAT (網路位址轉譯器) 裝置或防火牆連線。</p></td>
</tr>
<tr class="odd">
<td><p>啟用轉接來電記錄</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>指出是否將透過主幹來轉接來電記錄資訊。</p></td>
</tr>
<tr class="even">
<td><p>啟用轉寄 P-Asserted-Identity 資料</p></td>
<td><p>ForwardPAI</p></td>
<td><p>指出 P-Asserted-Identity (PAI) 標頭是否會和通話一起轉寄。PAI 標頭提供確認來電者身分識別的方法。</p></td>
</tr>
<tr class="odd">
<td><p>啟用輸出路由容錯移轉計時器</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>指出閘道未在 10 秒內接聽的撥出電話將會被路由傳送到下一個可用的主幹；如果沒有其他主幹，就會自動捨棄此電話。在網路和閘道回應速度緩慢的組織中，這可能會造成電話平白遭到捨棄。</p></td>
</tr>
<tr class="even">
<td><p>關聯的 PSTN 使用方式</p></td>
<td><p>PSTNUsages</p></td>
<td><p>指派給主幹的 PSTN 使用方式集合。</p></td>
</tr>
<tr class="odd">
<td><p>要測試的轉譯號碼</p></td>
<td><p>不適用</p></td>
<td><p>可用於進行主幹組態設定臨機測試的電話號碼。</p></td>
</tr>
<tr class="even">
<td><p>關聯的轉譯規則</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>套用到由「輸出路由」處理的電話 (路由傳送到 PBX 或 PSTN 目的地的電話) 的電話號碼轉譯規則集合。</p></td>
</tr>
<tr class="odd">
<td><p>撥打號碼轉譯規則</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>指派給主幹的撥出電話號碼轉譯規則集合。</p></td>
</tr>
<tr class="even">
<td><p>測試的電話號碼</p></td>
<td><p>不適用</p></td>
<td><p>可用於進行轉譯規則臨機測試的電話號碼。</p></td>
</tr>
<tr class="odd">
<td><p>撥打號碼</p></td>
<td><p>不適用</p></td>
<td><p>指出要測試的電話號碼是來電者的電話號碼。</p></td>
</tr>
<tr class="even">
<td><p>撥打的號碼</p></td>
<td><p>不適用</p></td>
<td><p>指出要測試的電話號碼是受話者的電話號碼。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lync Server Get-cstrunkconfiguration Cmdlet 支援未顯示在 Lync Server 控制台中的其他屬性。 如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> Cmdlet 的 [說明] 主題。



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台修改 SIP 主幹設定設定

1.  在 [Lync Server 控制台] 中，按一下 [ **語音路由**]，然後按一下 [ **主幹**設定]。

2.  在 [主幹組態]**** 索引標籤上，連按兩下要修改的主幹組態設定。請注意，一次只能編輯一個集合的設定。如果要針對多個集合進行相同的變更，請改用 Windows PowerShell。

3.  在 [ **編輯主幹** 設定] 對話方塊中，進行適當的選擇，然後按一下 **[確定]**。

4.  集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。

5.  在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。

6.  在 **[Microsoft Lync Server 2013 控制台]** 對話方塊中，按一下 **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

