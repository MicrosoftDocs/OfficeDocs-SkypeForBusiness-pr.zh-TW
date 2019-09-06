---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: 15e71446e6c0e15630125fb0e0169141f74f5cd0
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775147"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版（VL）上執行，並以標準桌上型電腦的形式接收相同的 Windows 更新與 OS 組建。

您可以依照下列各節中的討論來管理 Windows 更新：

## <a name="hands-off-approach"></a>動手做法 

- 根據預設，自動從 Windows 更新下載更新，並在下班期間安裝。
- 非推遲更新安裝 day-自動發行一次。
- 品質更新及驅動程式會自動下載並安裝。
- 功能更新。 請參閱後面的筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>商務用 Windows 更新（GPO 或 Intune）  

- [商務用 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)下載
- 更新是從 Windows Update 或您的 WSUS 下載，但在原始發行日期之後已設定延遲時間。
- 您可以使用多個 Ou 或篩選原則來建立「振鈴」，管理員可以在其中指定哪些裝置會先安裝品質更新，且稍後會進行安裝。 在任何情況下，都可以在系統子集上測試可靠性和效能，而不需要在 SCCM 中管理 Windows 更新，就能在整個部署中推出更新。
- 如果您想要頻寬管理和商務用 Windows 更新提供的控制，您可以同時[設定](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新。
- 功能更新。 請參閱後面的筆記。

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下載
- 就像是商務用 Windows 更新，但在每個 "震鈴" 或整個部署中都有以特定的 KB 為目標的額外選項。 每個更新都可以個別部署和測試，而不是只依賴延遲。
- 功能更新。 請參閱後面的筆記。

### <a name="feature-updates"></a>功能更新

與品質和不間斷更新不同，Windows 10 的「功能更新」（主要 OS 版本）只會在 Microsoft 測試並驗證 Microsoft 團隊會議室的特定更新功能之後安裝。 即使更新已發行至半年通道（如果您已將系統設定至該通道進行測試）或手動推送，Microsoft 房間系統裝置也不會允許安裝未經測試的更新。

Microsoft 團隊聊天室的功能是「不在使用中」的功能，且不會在 Windows 更新中安裝 Windows 更新或自動重新開機裝置。 系統會下載更新，並等待下一次重新開機來進行安裝。 除非有人手動重新開機，否則只會在每次自動重新開機時進行安裝。 Windows 更新在聊天室中應該是透明的，而且一般的操作應該不會被 Windows 更新中斷。

如果您選擇 [網域加入裝置]，請使用 [SCCM] 或 [WSUS]。 特別注意在上班時間內導致裝置更新或強制重新開機的原則或動作。 您部署中的系統不應在使用期間重新開機，或在使用時間期間透過 UI 發出有關 Windows 更新的警示，請檢查您的設定（如果發生此行為）。