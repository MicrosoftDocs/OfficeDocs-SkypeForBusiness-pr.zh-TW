---
title: Lync Server 2013： 檢視主幹組態資訊
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
ms.openlocfilehash: 102fb942397b8329da067d8c41c16ec393076a00
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Lync Server 2013 中檢視主幹組態資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

  - 主幹是否啟用媒體旁路。

  - 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。

  - 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝 Microsoft Lync Server 2013 時，為您建立的 SIP 主幹組態設定全域集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台檢視 SIP 主幹組態資訊

1.  在 Lync Server 控制台]，按一下 [**語音路由**，然後按一下 [**主幹組態**。

2.  在 [**主幹組態**] 索引標籤上，您會看到所有您主幹組態設定集合; 的清單針對每個集合中，您會看到的**名稱**、**範圍**、**狀態**和**媒體旁路**的屬性，以及數目**的 PSTN 使用方式**、**呼叫號碼規則**，以及**呼叫號碼規則**集合相關聯的值。 若要查看的主幹組態設定集合的其他詳細資料，按一下 [感興趣的集合，按一下 [**編輯**]，然後按一下**顯示詳細資料**。 請注意，您可以檢視僅適用於一次的主幹組態設定集合的詳細的資訊。

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 檢視 SIP 主幹組態資訊

SIP 主幹組態設定可檢視使用 Lync Server PowerShell 和 Get-cstrunkconfiguration cmdlet。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>若要檢視 SIP 主幹組態資訊

  - 若要檢視所有 SIP 主幹組態設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令並按 ENTER:
    
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

如需詳細資訊，請參閱[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

