---
title: 管理服務品質（QoS）
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 服務品質（QoS）是一些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817359"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>管理商務用 Skype Server 中的服務品質（QoS）


服務品質（QoS）是一些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。 QoS 最常用於頻寬有限的網路上：有大量網路資料包爭用相對較少的可用頻寬，服務品質會提供一種方式，讓管理員指派較高優先順序至資料包攜帶音訊或視頻資料。 透過將這些資料包設為較高的優先順序，音訊與視頻通訊可能會更快且中斷較少，因為涉及檔案傳輸、網頁流覽或資料庫備份等操作的網路會話。 這是因為用於檔案傳輸或資料庫備份的網路資料包已獲指派「最大努力」的優先順序。


> [!NOTE]  
> 一般來說，服務品質只適用于內部網路上的通訊會話。 當您實現 QoS 時，請將您的伺服器和路由器設定為支援資料包標記;不過，您可以將這些裝置設定為支援以特定方式進行資料包標記。 您無法假設在網際網路或其他網路上不支援該服務品質。 即使在其他網路上支援 Quality Services，也不會保證 QoS 的設定方式與您在網路上設定服務的方式相同。

商務用 Skype 伺服器不需要服務品質;如果您目前未使用 QoS，就不需要在安裝商務用 Skype Server 前安裝服務。 如果您在網路上遇到大量的資料包遺失，建議的方式就是緩解這個問題，就是要增加額外的頻寬。 如果不可能增加更多頻寬，您可能會想要改為執行服務品質。

商務用 Skype Server 提供完整的服務品質支援：這表示已使用 QoS 的組織可以輕鬆地將商務用 Skype 伺服器整合到現有的網路基礎結構中。 若要這樣做，您必須執行下列工作：

  - [啟用不是以 Windows 為基礎的裝置的 QoS](enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，系統會針對執行其他作業系統的電腦和其他裝置（例如 Iphone）停用 QoS。 雖然您可以使用商務用 Skype 伺服器來啟用和停用裝置的服務品質，但您通常無法使用該產品來修改這些裝置所使用的 DSCP 代碼。

  - [為您的會議、應用程式及中繼伺服器設定埠範圍及服務品質原則](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須為不同的資料包類型（例如音訊和影片）保留一組獨特的埠。 在商務用 Skype Server 中，您不可以啟用或停用服務品質，比如說將屬性值設定為 True 或 False。 相反地，您必須先設定埠範圍，然後建立並套用群組原則，才能啟用服務品質。 如果您稍後決定不使用 QoS，您只要移除適當的群組原則物件，就可以「停用」服務品質。

  - [為您的邊緣伺服器設定埠範圍和服務品質原則](configuring-port-ranges-for-your-edge-servers.md)。 雖然不必要，但您可以將邊緣伺服器設定為使用與其他伺服器相同的埠範圍。 只有在邊緣伺服器的內部端，才能設定服務品質原則。 那是因為服務品質是專為在您的內部網路（而不是在網際網路）上使用而設計。

- [在商務用 Skype Server 中針對用戶端設定埠範圍和服務品質原則](configuring-port-ranges-for-your-skype-clients.md) 這些埠範圍只適用于用戶端電腦，且通常與您伺服器上設定的埠範圍不同。 請注意，商務用 Skype Server 不支援 Windows 10 以外的 Windows 作業系統 QoS。


