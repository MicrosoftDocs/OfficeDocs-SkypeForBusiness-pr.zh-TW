---
title: 為不是以 Windows 為基礎的裝置啟用 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何為組織中使用 Windows 以外作業系統的裝置啟用 QoS。
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814173"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>在不是以 Windows 為基礎的裝置上啟用商務用 Skype Server 中的 QoS


當您安裝商務用 Skype Server、服務品質 (QoS) 將不會為組織中使用 Windows 以外作業系統的任何裝置啟用。 您可以在商務用 Skype ServerManagement 命令介面中執行下列命令，以進行驗證：

    Get-CsMediaConfiguration

假設您未對媒體設定設定進行任何變更，您應該會收到類似以下的資訊：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 屬性設定為 False (如先前的輸出所) 表示服務品質未針對使用 Windows 以外之作業系統的電腦和裝置啟用。

若要在全域範圍啟用服務品質，請從商務用 Skype Server 管理命令介面中執行下列命令：

    Set-CsMediaConfiguration -EnableQoS $True

先前的命令會啟用全域範圍的 QoS；但需要注意的是，媒體組態設定也會套用至網站範圍。 如果您需要啟用網站的服務品質，您必須在呼叫 CsMediaConfiguration 時包含設定設定的身分識別。 例如，此命令會啟用 Redmond 網站的 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 您是否需要啟用網站範圍的 QoS？ 答案是不一定。 指派至網站範圍的設定會優先於指派至全域範圍的設定。 假設您已在全域範圍啟用 QoS，但在 Redmond 網站) 的網站範圍 (停用。 在此情況下，會停用 Redmond 網站的服務品質;這是因為網站設定會優先。 若要啟用 Redmond 網站的 QoS，您必須使用套用至該網站的媒體設定設定來執行。


如果您想要同時針對所有媒體設定設定啟用 QoS (不論範圍) ，請從 LSkype for Business Server Management Shell 中執行此命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

您可以對使用 Windows 以外之作業系統的裝置停用 QoS，方法是將 EnableQoS 屬性的值設為 False。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

這使您能夠在網路的某些部分停用服務品質的同時，於網路的其他部分啟用 QoS (例如在 Redmond 網站上)。

僅能使用 Windows PowerShell 來啟用及停用 QoS。 在商務用 Skype Server [控制台] 中無法使用這些選項。

> [!NOTE]
> IOS 版本6.17 和更新版本的商務用 Skype 用戶端現在支援 QoS。  此 QoS 功能僅適用于直接註冊到受管理網路上內部 Skype for business 或 Lync 集區伺服器的商務用 Skype 用戶端和 IP 電話裝置。 QoS 不適用於透過網際網路路由傳送的流量。



