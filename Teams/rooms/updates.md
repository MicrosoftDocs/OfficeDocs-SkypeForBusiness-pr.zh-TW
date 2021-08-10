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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 系統管理員可以瞭解如何管理Windows更新Windows更新Microsoft Teams 會議室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67144ff29077a3dec6be79b9b68efb1162d31a9069b3436b29f9ac50a4857914
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275959"
---
# <a name="manage-windows-updates"></a>管理Windows更新

Microsoft Teams 會議室于 Windows 10 企業版 IoT 或 VL Windows 10 企業版 (VL) 上執行，並Windows與標準桌上型電腦相同的更新和作業系統建立。

Windows如下列各節所述，可以管理更新：

## <a name="hands-off-approach"></a>離開方法 

- 根據預設，更新會直接從 Windows下載，並會在非工作時間安裝。
- 不可延遲的更新會自動在發行的第一天安裝。
- 品質更新和驅動程式會自動下載並安裝一天。
- 功能更新。 請參閱下列筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows商務用更新 (GPO 或 Intune)   

- [Windows商務用更新](/windows/deployment/update/waas-manage-updates-wufb)下載
- 更新會從更新Windows您的 WSUS 下載，但已配置的延遲會過原始發行日期。
- 您可以使用多個 OUs 或篩選後的政策來建立部署「圈」，讓系統管理員可以指定哪些裝置會先安裝品質更新，哪些裝置稍後再安裝。 在整個部署中推出更新之前，可以在系統子集上測試可靠性和Windows，而不需要在 Configuration Manager 中管理Windows更新。
- 如果您想要同時Windows頻寬管理和商務用更新的控制權，可以同時[](/windows/deployment/update/waas-integrate-wufb)Windows商務用更新。
- 功能更新。 請參閱下列筆記。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下載
- 就像Windows商務用更新一樣，但在每個「響鈴」或整個部署中，有一個額外的選項是將特定 KB 作為目標。 每個更新都可以依需要個別部署和測試，而不是只仰賴延遲。
- 功能更新。 請參閱下列筆記。

### <a name="feature-updates"></a>功能更新

與品質與不可延遲更新不同，Windows 10主要作業系統版本 (的) 功能更新只會在 Microsoft 測試並驗證使用 Microsoft Teams 會議室 的給定更新功能之後安裝。 即使您將更新發行至 Semi-Annual 通道 (或已設定目標，如果您將系統設定為測試) 或手動推送的通道，Microsoft Room Systems 裝置也不會允許安裝未測試的更新。

Microsoft Teams 會議室「開箱即用」功能，而且不會針對更新自動安裝 Windows 更新或重新開機Windows裝置。 系統會下載更新，並等待下次重新開機以安裝更新。 除非有人手動重新開機，安裝只會在自動夜間重新開機時執行。 Windows更新應透明地在聊天室中，而且正常作業不應受到更新Windows干擾。

如果您選擇將加入裝置網域，請使用 Microsoft Endpoint Configuration Manager WSUS。 請特別注意導致裝置更新或工作時間強制重新開機的政策或動作。 部署中的系統不應在使用期間重新開機，或提醒Windows使用時間期間，在 UI 上更新更新，如果發生此行為，請檢查您的組組。