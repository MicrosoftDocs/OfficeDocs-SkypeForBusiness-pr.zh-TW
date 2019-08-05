---
title: 啟用不是以 Windows 為基礎的裝置的 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解如何針對貴組織中使用 Windows 以外的作業系統的裝置啟用 QoS。
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188530"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>在商務用 Skype Server 中啟用 QoS (適用于不以 Windows 為基礎的裝置)


當您安裝商務用 Skype Server 時, 貴組織中任何使用 Windows 以外作業系統的裝置, 都不會啟用服務品質 (QoS)。 您可以從商務用 Skype ServerManagement Shell 中執行下列命令, 以進行驗證:

    Get-CsMediaConfiguration

如果您沒有對媒體設定設定進行任何變更, 您應該會看到類似以下的資訊:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 屬性設定為 False (如前面的輸出), 表示沒有針對使用 Windows 以外的作業系統的電腦和裝置啟用服務品質。

若要在全域範圍啟用服務品質, 請在商務用 Skype Server Management Shell 中執行下列命令:

    Set-CsMediaConfiguration -EnableQoS $True

上述命令可在全域範圍內啟用 QoS;不過, 請務必注意, 媒體配置設定也可以套用到網站範圍。 如果您需要為網站啟用服務品質, 您必須在呼叫 CsMediaConfiguration 時包含設定設定的身分識別。 例如, 這個命令可為雷蒙德網站啟用 QoS:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 您是否需要在網站範圍中啟用 QoS？ 視情況而定。 指派給網站範圍的設定會優先于指派給全域範圍的設定。 假設您已在全域範圍啟用 QoS, 但在網站範圍停用 (針對雷德蒙的網站)。 在這種情況下, 雷德蒙者網站的服務品質會停用;這是因為 [網站設定] 的優先順序。 若要啟用雷德蒙網站的 QoS, 您必須使用套用至該網站的媒體設定設定來執行此操作。


如果您想要同時啟用所有媒體設定的 QoS (無論範圍為何), 請在商務用 LSkype Server Management Shell 中執行此命令:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

您可以透過將 EnableQoS 屬性的值設定為 False, 來停用使用 Windows 以外作業系統的裝置的 QoS。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

這可讓您在網路的某些部分 (例如, 在雷德蒙的網站) 上實現 QoS, 同時在網路的其他部分停止服務品質。

QoS 只能使用 Windows PowerShell 來啟用和停用。 在商務用 Skype Server 控制台中無法使用這些選項。


