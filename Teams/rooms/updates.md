---
title: 管理Windows更新Microsoft Teams 會議室
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
ms.assetid: ''
description: 系統管理員可以瞭解如何管理Windows更新Windows更新Microsoft Teams 會議室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c904db6b168280619b203a1327d6477736077efe
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015003"
---
# <a name="manage-windows-updates"></a>管理Windows更新

Microsoft Teams 會議室于 Windows 10 企業版或 VL Windows 10 企業版 (VL) 上執行，並Windows與標準桌上型電腦相同的更新和作業系統建立。

Windows更新可以管理，如下列各節所述：

## <a name="hands-off-approach"></a>離開方法 

- 根據預設，更新會直接從 Windows下載，並會在非工作時間安裝。
- 不可延遲的更新會在發行的第一天自動安裝。
- 品質更新和驅動程式會自動下載並安裝一天。
- 功能更新。 請參閱下列筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows GPO 或 Intune (商務用更新)   

- [Windows商務用更新](/windows/deployment/update/waas-manage-updates-wufb)下載
- 更新會從 Windows 或您的 WSUS Windows Server Update Services (下載) 但已配置的延遲已過原始發行日期。
- 您可以使用多個 OUs 或篩選後的政策來建立部署「圈」，讓系統管理員Teams 會議室哪些裝置先安裝品質更新，哪些裝置稍後安裝。 在整個部署中推出更新之前，可以在裝置子集上測試可靠性和Windows，而不需要在 Configuration Manager 中管理Windows更新。
- 如果您想要同時Windows頻寬管理和商務用更新的控制權，可以同時[](/windows/deployment/update/waas-integrate-wufb)Windows商務用更新。
- 功能更新。 請參閱下列筆記。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下載
- 就像Windows商務用更新，但在每個「響鈴」或整個部署中，有另一個將特定 KB 作為目標的選項。 每個更新都可以依需要個別部署和測試，而不是只仰賴延遲。
- 功能更新。 請參閱下列筆記。

### <a name="feature-updates"></a>功能更新

與品質與不可延遲更新不同，Windows 10主要作業系統版本 (的 「功能更新」) 只有在 Microsoft 測試並驗證使用 Microsoft Teams 會議室 的給定更新功能之後，才能安裝。 即使您將更新發行至 Semi-Annual 通道 (或已設定目標，如果您有系統設定為該通道以測試) 或手動推送，Microsoft Teams 會議室 也不允許安裝未測試的更新。

Microsoft Teams 會議室使用「開箱即用」函數。 Teams 會議室下載更新，並等待下次重新開機以安裝更新。 除非有人手動重新開機，安裝只會在自動夜間重新開機時執行。 Windows聊天室中的更新應該是透明的，而且正常作業不應受到更新Windows干擾。

如果您選擇將加入裝置網域，您可以使用 Microsoft Endpoint Configuration Manager WSUS。 請特別注意導致裝置更新或工作時間強制重新開機的政策或動作。 Teams 會議室使用期間不應重新開機，或提醒Windows使用時間期間，Windows UI 更新。 如果發生此行為，請檢查您的組組。
