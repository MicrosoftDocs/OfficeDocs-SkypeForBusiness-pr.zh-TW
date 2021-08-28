---
title: '管理服務品質 (QoS) '
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 服務品質 (QoS) 是某些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。
ms.openlocfilehash: 33c580e61be0dcd2a5a193a654294a5ea9087d12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612162"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>在商務用 Skype Server 中管理服務品質 (QoS) 


服務品質 (QoS) 是某些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。 QoS 最常用於頻寬有限的網路：有大量網路資料包會爭用相對的可用頻寬量，服務品質可為系統管理員提供一種方法，讓系統管理員可以將較高優先順序指派給攜帶音訊或視頻資料的封包。 透過將這些封包以較高優先順序傳送，音訊和影片通訊的速度可能會更快，且中斷較低，其方式就是檔案傳輸、網頁流覽或資料庫備份等相關的網路會話。 這是因為用於進行檔案傳輸或資料庫備份的網路封包是以「最大努力」優先順序指派。


> [!NOTE]  
> 一般來說，服務品質只適用于內部網路上的通訊會話。 當您執行 QoS 時，會設定您的伺服器和路由器以支援封包標記;不過，您可以設定這些裝置以特定方式支援封包標記。 您無法假定在網際網路或其他網路上都支援服務品質。 即使其他網路上支援品質的服務，也無法保證 QoS 會以您在網路上設定服務的相同方式來設定。

商務用 Skype Server 不需要服務品質;如果您目前未使用 QoS 您不需要在安裝商務用 Skype Server 之前安裝服務。 如果您的網路上有大量的封包遺失，建議的方法是緩解此問題，以增加額外的頻寬。 如果無法新增更多的頻寬，您可能想要改為執行服務品質。

商務用 Skype Server 為服務品質提供完整支援：也就是說，已使用 QoS 的組織可以輕鬆地將商務用 Skype Server 整合至現有的網路基礎結構。 為了達到此目的，您必須執行下列工作：

  - [為不是以 Windows 為基礎的裝置啟用 QoS](enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，系統會停用電腦及其他裝置的 QoS，例如執行其他作業系統的 Iphone) 等 (。 雖然您可以使用商務用 Skype Server 來啟用及停用裝置的服務品質，但通常無法使用產品修改這些裝置所使用的 DSCP 碼。

  - [針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須為不同的封包類型（如音訊和影片）預約一組獨特的埠。 使用商務用 Skype Server 您未啟用或停用服務品質，例如，將屬性值設定為 True 或 False。 相反地，您可以設定埠範圍，然後建立及套用群組原則，以啟用服務品質。 如果您稍後決定不使用 QoS 您只要移除適當的群組原則物件，就可以「停用」服務品質。

  - 設定[Edge server 的埠範圍及服務品質原則](configuring-port-ranges-for-your-edge-servers.md)。 您可以將 Edge server 設定成使用與其他伺服器相同的埠範圍，但這不是必要的。 只應該針對 Edge server 的內部端執行服務品質原則的設定。 這是因為服務品質已設計為用於內部網路，而不是在網際網路上。

- 設定[商務用 Skype Server 中用戶端的埠範圍和服務品質原則](configuring-port-ranges-for-your-skype-clients.md) 這些埠範圍只適用于用戶端電腦，通常與伺服器上設定的埠範圍不同。 請注意，商務用 Skype Server 不支援 Windows 10 以外的 Windows 作業系統 QoS。


