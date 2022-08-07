---
title: 管理適用于 Microsoft Teams 會議室 的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: 管理員可以瞭解如何管理 Microsoft Teams 會議室 的 Windows 更新 和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272178"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft Teams 會議室在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行，並收到與標準桌上型電腦相同的 Windows 更新 和作業系統組建。

Windows 更新可依照下列各節所述進行管理：

## <a name="hands-off-approach"></a>免持方式 

- 根據預設，更新會直接從 Windows 下載更新自動安裝，並在下班時間安裝。
- 不可延後更新自動安裝第一天發行版本。
- 品質更新和驅動程式會自動下載並安裝一天。
- 功能更新。 請參閱後續的筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>商務用 Windows 更新 (GPO 或 Intune)   

- [商務用 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb)下載
- 更新是從 Windows Update 或您的 Windows Server Update Services (WSUS) 下載，但已設定超過原始發行日期的延遲。
- 您可以使用多個 OU 或篩選的原則來建立部署「頻道」，讓系統管理員可以指定哪些Teams 會議室裝置先安裝品質更新，然後再安裝哪些裝置。 可靠性和效能可先在一部分裝置上測試，然後在整個部署中推出更新，而不需要在Configuration Manager中管理 Windows 更新的負荷。
- 如果您需要頻寬管理和商務用 Windows 更新提供的控制措施，可以[同時](/windows/deployment/update/waas-integrate-wufb)設定 WSUS 和商務用 Windows 更新。
- 功能更新。 請參閱後續的筆記。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)下載
- 很像商務用 Windows Update，但要讓特定 KB 在每個「通道」或整個部署內設定特定 KB 目標的其他選項。 每個更新都可以個別部署和測試，而不是只依賴延遲。
- 功能更新。 請參閱後續的筆記。

### <a name="feature-updates"></a>功能更新

不同于品質與不可延遲的更新，Windows 10「功能更新」 (主要作業系統版本) 只會在 Microsoft 測試並驗證特定的Microsoft Teams 會議室更新功能之後才安裝。 即使更新已發行至Semi-Annual通道 (或已設定目標，如果您已將系統設定為該通道以測試) 或手動推送，Microsoft Teams 會議室不會允許安裝未經測試的更新。

Microsoft Teams 會議室用免持即用的方法來「開箱即用」函數。 Teams 會議室下載更新，並等待下一次重新開機以安裝更新。 除非有人手動重新開機，否則安裝只會在自動夜間重新開機時進行。 Windows 更新在會議室中應該是透明的，正常運作不應受到 Windows 更新干擾。

如果您加入宣告裝置網域，您可以使用 Microsoft Endpoint Configuration Manager 或 WSUS。 特別注意導致裝置更新或在上班時間強制重新開機的原則或動作。 Teams 會議室在使用期間不應該重新開機，或在使用時段內透過 UI 對 Windows 更新發出警示。 如果發生該行為，請檢閱您的設定。
