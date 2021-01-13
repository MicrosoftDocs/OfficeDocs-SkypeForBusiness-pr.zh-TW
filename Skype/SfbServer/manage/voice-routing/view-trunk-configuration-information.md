---
title: 在商務用 Skype Server 中查看主幹設定資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826163"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看主幹設定資訊

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。

- 主幹是否啟用媒體旁路。
- 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。
- 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。

**使用商務用 Skype Server 控制台來查看 SIP 主幹設定資訊**

1. 在商務用 Skype Server 控制台中，依序按一下 [ **語音路由**] 和 [ **主幹** 設定]。
2. 在 [ **主幹** 設定] 索引標籤上，您將會看到所有主幹設定的集合，也就是針對每個集合，您會看到 **名稱**、 **範圍**、 **狀態** 及 **媒體旁路** 屬性的值，以及 **PSTN 使用** 的數目、 **呼叫號碼規則**，以及與集合關聯的 **呼叫編號規則** 。 若要查看主幹設定設定集合的其他詳細資料，請按一下相關集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。 請注意，您一次只能查看一個主幹設定設定集合的詳細資訊。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 SIP 主幹設定資訊

您可以使用商務用 Skype Server PowerShell 和 Get-CsTrunkConfiguration Cmdlet 來查看 SIP 主幹設定設定。 您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at https://go.microsoft.com/fwlink/p/?linkId=255876 。 請取代或移除此連結。


**若要查看 SIP 主幹設定資訊**

若要查看所有 SIP 主幹設定設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：

```powershell
Get-CsTrunkConfiguration
```

如此將傳回類似如下的資訊：

```console
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
```
如需詳細資訊，請參閱 [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。



