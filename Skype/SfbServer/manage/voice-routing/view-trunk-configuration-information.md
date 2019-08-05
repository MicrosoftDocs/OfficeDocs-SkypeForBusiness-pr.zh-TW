---
title: 在商務用 Skype Server 中查看幹線設定資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 exchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186994"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看幹線設定資訊

SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 exchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。

- 是否應該在 trunks 上啟用媒體旁路。
- 傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。
- 每個幹線是否都需要安全的即時通訊協定 (SRTP) 加密。

當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。 此外, 管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 上建立自訂設定集合。

**使用商務用 Skype Server 控制台來查看 SIP 幹線設定資訊**

1. 在商務用 Skype Server [控制台] 中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。
2. 在 [**幹線**設定] 索引標籤上, 您會看到所有中繼設定集合的清單;針對每個集合, 您會看到**名稱**、**範圍**、**狀態**及**媒體旁路**屬性的值, 以及**PSTN 使用量**數、**通話編號規則**, 以及相關聯的**號碼規則**。集合。 若要查看主幹設定設定集合的其他詳細資料, 請按一下感興趣的集合, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。 請注意, 您可以一次只查看一個主幹設定設定集合的詳細資訊。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 SIP 幹線設定資訊

您可以使用商務用 Skype Server PowerShell 和 New-cstrunkconfiguration Cmdlet 來查看 SIP 幹線設定設定。 此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱 Lync Server Windows PowerShell 博客文章「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 http://go.microsoft.com/fwlink/p/?linkId=255876。 [取代] 或 [移除] 此連結。


**若要查看 SIP 中繼配置資訊**

若要查看所有 SIP 主幹設定設定的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER 鍵:

`Get-CsTrunkConfiguration`

這會傳回如下所示的資訊:

```
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
如需詳細資訊, 請參閱[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) Cmdlet 的說明主題。



