---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103199"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 團隊聊天室會在 Windows 10 Enterprise IoT 或 Windows 10 Enterprise (VL) 上執行，並以標準的桌面接收相同的 Windows 更新和 OS 組建。

Windows 更新可透過幾種不同的方式來管理：

## <a name="hands-off-approach"></a>不用動手的做法 
- 更新可從 Windows 直接下載，並在下班時間內安裝更新。 若未變更設定，此為預設狀態。
- 非可延遲的更新將會自動安裝第一天的版本。 
- 品質更新及驅動程式將會自動下載並安裝第一天。 
- 功能更新。 請參閱下列其他附注。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows 更新](/windows/deployment/update/waas-manage-updates-wufb) (GPO 或 Intune)    
- 更新會從 WU 或您的 WSUS 下載，但已設定的延遲超過 KB 的原始發行日期。 
- 與多個 OU 或篩選的原則組合在一起，可讓您建立部署 "振鈴"，讓系統管理員可以指定哪些裝置會先安裝品質更新，以及將在稍後安裝哪些裝置。 這可讓您在整個部署期間進行可靠性和效能測試，而不需要在 Microsoft 端點設定管理員中管理 Windows 更新（範例）。
- 如果您想要同時進行頻寬管理，以及 Windows 的 Windows 更新所提供的控制，WSUS 和 Windows 更新可在 [同一時間進行設定](/windows/deployment/update/waas-integrate-wufb) 。
- 功能更新。 請參閱下列其他附注。

## <a name="wsusconfiguration-manager"></a>[WSUS/設定管理員](/windows/deployment/update/waas-manage-updates-configuration-manager)
- 很像是企業的 Windows 更新，但有其他選項，針對每個「震鈴」或整個部署中的特定 KB。 每個更新都可以個別地部署及測試，而不只是僅依賴延遲。 
- 功能更新。 請參閱下列其他附注。


### <a name="feature-updates"></a>功能更新

與品質和非 Deferable 的更新不同的是，Windows 10 「功能更新」會 (主作業系統版本) ，只會在 Microsoft 測試及驗證 Microsoft 團隊會議室的指定更新功能之後安裝。 即使將系統設為 Semi-Annual 通道 (或目標，如果您已將系統設為測試) ，甚至是以您自己的嘗試或設定手動推入，它也不會允許安裝，直到我們最後一次刪除該塊為止。

Microsoft 團隊會議室「現成」，使用「動手」方法，不會因為 Windows 更新而自動安裝 Windows Update 或重新開機裝置。 不過，系統可能會下載更新，並等待下一次重新開機進行安裝。 除非有人手動重新開機，否則應該會在每次自動重新開機時進行安裝。 在會議室中，windows 更新應該是透明的，而使用者介面絕對不應該中斷 Windows 更新。

如果您加入宣告網域，請使用 Microsoft 端點設定管理員或 WSUS，並特別注意可能導致裝置安裝更新或在上班時間強制重新開機的原則或動作。 如果您的部署在使用期間重新開機系統，或透過 UI 的 Windows 更新發出警示，您會想要查看您的設定。