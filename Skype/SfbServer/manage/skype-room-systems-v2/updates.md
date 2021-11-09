---
title: 管理 Microsoft Teams 會議室的 Windows 更新
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft Teams 會議室的 Windows 更新
ms.openlocfilehash: 1a5e665546c00525939585f4655fcdf404e5786f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859990"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft Teams 會議室會在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行，並以標準的桌面接收相同的 Windows 更新和 OS 組建。

Windows您可以透過幾種不同的方式來管理更新：

## <a name="hands-off-approach"></a>不用動手的做法 
- 更新可以直接從 Windows 更新中下載，並在下班時間安裝。 若未變更設定，此為預設狀態。
- 非可延遲的更新將會自動安裝第一天的版本。 
- 品質更新及驅動程式將會自動下載並安裝第一天。 
- 功能更新。 請參閱下列其他附注。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows 商務](/windows/deployment/update/waas-manage-updates-wufb) (GPO 或 Intune) 更新   
- 更新會從 WU 或您的 WSUS 下載，但已設定的延遲超過 KB 的原始發行日期。 
- 與多個 OU 或篩選的原則組合在一起，可讓您建立部署 "振鈴"，讓系統管理員可以指定哪些裝置會先安裝品質更新，以及將在稍後安裝哪些裝置。 這可讓您在整個部署期間進行可靠性和效能測試，而不需要在 Microsoft Endpoint Configuration Manager 中管理 Windows 更新等負載。
- 如果您想要進行頻寬管理，以及商務 Windows 更新所提供的控制，則可以同時[設定](/windows/deployment/update/waas-integrate-wufb)Windows 的 WSUS 和更新的商務更新。
- 功能更新。 請參閱下列其他附注。

## <a name="wsusconfiguration-manager"></a>[WSUS/設定管理員](/windows/deployment/update/waas-manage-updates-configuration-manager)
- 很像是 Windows 的商務更新，但有其他的選項，針對每個「環」或整個部署中的特定 KB。 每個更新都可以個別地部署及測試，而不只是僅依賴延遲。 
- 功能更新。 請參閱下列其他附注。


### <a name="feature-updates"></a>功能更新

與品質和非 Deferable 的更新不同 Windows 10 的是，「功能更新」 (主要 OS 發行) 只會在 Microsoft 測試及驗證具有 Microsoft Teams 會議室的指定更新功能之後安裝。 即使將系統設為 Semi-Annual 通道 (或目標，如果您已將系統設為測試) ，甚至是以您自己的嘗試或設定手動推入，它也不會允許安裝，直到我們最後一次刪除該塊為止。

Microsoft Teams會議室 "現成"，使用「動手」方法，不會因為 Windows 更新而自動安裝 Windows 更新或重新開機裝置。 不過，系統可能會下載更新，並等待下一次重新開機進行安裝。 除非有人手動重新開機，否則應該會在每次自動重新開機時進行安裝。 Windows更新在會議室中應該是透明的，使用者介面絕對不應該中斷 Windows 更新。

如果您加入宣告網域，請使用 Microsoft Endpoint Configuration Manager 或 WSUS，並特別注意可能導致裝置安裝更新或在上班時間強制重新開機的原則或動作。 如果您的部署中有系統在使用期間重新開機，或在透過 UI Windows 更新時發出警示，您會想要查看您的設定。