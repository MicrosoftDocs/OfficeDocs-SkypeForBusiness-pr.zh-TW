---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243275"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行, 並以標準桌面接收相同的 Windows 更新與 OS 組建。

您可以透過幾種不同的方式來管理 Windows 更新:

## <a name="hands-off-approach"></a>動手做法 

- 您可以從 Windows 自動下載更新, 並在下班期間安裝更新。 這是預設的配置。
- 非推遲更新安裝 day-自動發行一次。
- 品質更新及驅動程式會自動下載並安裝。
- 功能更新。 請參閱後面的筆記。

## <a name="windows-updates-for-business-gpo-or-intune"></a>商務用 Windows 更新 (GPO 或 Intune)  

- [商務用 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)下載
- 更新是從 WU 或您的 WSUS 下載, 但已設定的延遲超過 KB 的原始發行日期。
- 與多個 OU 或篩選的原則搭配使用, 您可以建立部署 "鈴響", 管理員可以在這裡指定哪些裝置會先安裝品質更新, 以及稍後要安裝哪些裝置。 這可讓您在整個部署期間進行可靠性和效能測試, 而不需要在 SCCM 中管理 Windows 更新的額外負荷 (例如)。
- 如果您想要頻寬管理和商務用 Windows 更新提供的控制, 您可以同時[設定](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新。
- 功能更新。 請參閱後面的筆記。

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下載
- 就像是商務用 Windows 更新, 但在每個 "震鈴" 或整個部署中都有以特定的 KB 為目標的額外選項。 每個更新都可以個別部署和測試, 而不是只依賴延遲。
- 功能更新。 請參閱後面的筆記。

### <a name="feature-updates"></a>功能更新

與品質和不間斷更新不同, Windows 10 的「功能更新」 (主要 OS 版本) 只會在 Microsoft 測試並驗證 Microsoft 團隊會議室的特定更新功能之後安裝。 即使更新已發行至半年通道 (如果您已將系統設定至該通道進行測試) 或手動推送, Microsoft 房間系統裝置也不會允許安裝未經測試的更新。

Microsoft 團隊聊天室是「不在使用中」的「不在使用中」的方式, 不會在 Windows 更新中安裝 Windows 更新或自動重新開機裝置。 系統可能會下載更新, 並等待下一次重新開機來安裝。 除非有人手動重新開機, 否則系統會在自動重新開機時進行安裝。 Windows 更新在聊天室中應該是透明的, 而使用者介面不應該被 Windows 更新中斷。

如果您加入宣告網域的裝置, 請使用 SCCM 或 WSUS。 特別注意策略或動作, 可能會導致裝置安裝更新, 或在營業期間強制重新開機。 您部署中的系統不應在使用期間重新開機, 或在使用時間期間透過 UI 發出有關 Windows 更新的警示, 請檢查您的設定 (如果發生此行為)。