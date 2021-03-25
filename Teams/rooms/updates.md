---
title: 管理 Microsoft Teams 會議室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 系統管理員可以瞭解如何管理 Microsoft Teams 會議室的 Windows 更新和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117361"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft Teams 會議室在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行，並接收與標準桌上型電腦相同的 Windows 更新和作業系統建立。

如下列各節所述，可以管理 Windows 更新：

## <a name="hands-off-approach"></a>離開方法 

- 根據預設，更新會直接從 Windows Updates 自動下載，並會在非工作時間安裝。
- 不可延遲的更新會自動在發行的第一天安裝。
- 品質更新和驅動程式會自動下載並安裝一天。
- 功能更新。 請參閱下列筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>商務用 Windows 更新 (GPO 或 Intune)   

- [下載商務用 Windows](/windows/deployment/update/waas-manage-updates-wufb) 更新
- 更新會從 Windows Update 或您的 WSUS 下載，但已配置的延遲會過原始發行日期。
- 您可以使用多個 OUs 或篩選後的政策來建立部署「圈」，讓系統管理員可以指定哪些裝置會先安裝品質更新，哪些裝置稍後再安裝。 在整個部署中推出更新之前，您可以在系統子集上測試可靠性和績效，而不需要在 Configuration Manager 中管理 Windows 更新。
- 如果您同時想要頻寬管理和商務用 Windows[](/windows/deployment/update/waas-integrate-wufb)更新提供的控制項，可以同時配置 WSUS 和商務用 Windows 更新。
- 功能更新。 請參閱下列筆記。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下載
- 就像商務用 Windows Update 一樣，但在每個「響鈴」或整個部署中，有一個額外的選項是將特定 KB 作為目標。 每個更新都可以依需要個別部署和測試，而不是只仰賴延遲。
- 功能更新。 請參閱下列筆記。

### <a name="feature-updates"></a>功能更新

與品質與不可延遲更新不同，Windows 10「功能更新」 (主要作業系統版本) 只會在 Microsoft 測試及驗證 Microsoft Teams 會議室的給定更新功能後安裝。 即使您將更新發行至 Semi-Annual 通道 (或已設定目標，如果您有系統設定至該通道以測試) 或手動推送，Microsoft Room Systems 裝置也不會允許安裝未測試的更新。

Microsoft Teams 會議室功能「開箱即用」，而且不會安裝 Windows Update 或自動重新開機 Windows Update 的裝置。 系統會下載更新，並等待下次重新開機以安裝更新。 除非有人手動重新開機，安裝只會在自動夜間重新開機時執行。 Windows 更新在聊天室中應該是透明的，Windows 更新不應中斷正常作業。

如果您選擇將加入裝置網域，請使用 Microsoft 端點組組管理員或 WSUS。 請特別注意導致裝置更新或工作時間強制重新開機的政策或動作。 部署中的系統不應在使用期間重新開機，或在使用時間期間提醒您有關 Windows 更新的提醒，如果發生此行為，請檢查您的組配置。