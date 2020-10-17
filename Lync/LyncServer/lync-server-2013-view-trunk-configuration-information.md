---
title: Lync Server 2013：查看主幹設定資訊
description: Lync Server 2013：查看主幹設定資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b4e1d3063d65f8c27ad231f063249748046f759
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565429"
---
# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看主幹設定資訊

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

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台查看 SIP 主幹設定資訊

1.  在 [Lync Server 控制台] 中，按一下 [ **語音路由** ]，然後按一下 [ **主幹**設定]。

2.  在 [ **主幹** 設定] 索引標籤上，您將會看到所有主幹設定的集合，也就是針對每個集合，您會看到 **名稱**、 **範圍**、 **狀態**及 **媒體旁路** 屬性的值，以及 **PSTN 使用**的數目、 **呼叫號碼規則**，以及與集合關聯的 **呼叫編號規則** 。 若要查看主幹設定設定集合的其他詳細資料，請按一下相關集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。 請注意，您一次只能查看一個主幹設定設定集合的詳細資訊。

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 SIP 主幹設定資訊

您可以使用 Lync Server PowerShell 和 Get-CsTrunkConfiguration Cmdlet 來查看 SIP 主幹設定設定。 您可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>若要查看 SIP 主幹設定資訊

  - 若要查看所有 SIP 主幹設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsTrunkConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

如需詳細資訊，請參閱 [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

