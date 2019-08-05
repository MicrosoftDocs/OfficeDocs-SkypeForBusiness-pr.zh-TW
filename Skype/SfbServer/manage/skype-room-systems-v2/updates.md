---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 7ea7197752b42db788b2f67b9ae1c80cdad80177
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188518"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行, 並以標準桌面接收相同的 Windows 更新與 OS 組建。

您可以透過幾種不同的方式來管理 Windows 更新:

## <a name="hands-off-approach"></a>動手做法 
- 您可以從 Windows 自動下載更新, 並在下班期間安裝更新。 如果沒有對設定進行任何變更, 這就是預設狀態。
- 非推遲更新會自動安裝 day-其中一個發行程式。 
- 品質更新及驅動程式將會自動下載並安裝一次。 
- 功能更新。 請參閱下方的其他記事。 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[商務用 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)(GPO 或 Intune)   
- 更新是從 WU 或您的 WSUS 下載, 但已設定的延遲超過 KB 的原始發行日期。 
- 與多個 OU 或篩選的原則結合, 這可讓您建立部署「鈴響」, 管理員可以指定哪些裝置會先安裝品質更新, 且稍後會安裝哪些裝置。 這可讓您在整個部署期間進行可靠性和效能測試, 而不需要在 SCCM 中管理 Windows 更新的額外負荷 (例如)。
- 如果您想要頻寬管理和 Windows 相關的 Windows 更新提供, 您可以同時[設定](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和商務用 windows 更新。
- 功能更新。 請參閱下方的其他記事。

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 就像是商務用 Windows 更新, 但在每個 "震鈴" 或整個部署中都有以特定的 KB 為目標的額外選項。 每個更新都可以個別部署和測試, 而不是只依賴延遲。 
- 功能更新。 請參閱下方的其他記事。


### <a name="feature-updates"></a>功能更新

與品質和非 Deferable 更新不同, Windows 10 的「功能更新」 (主要 OS 版本) 只會在 Microsoft 測試並驗證 Microsoft 團隊會議室的特定更新功能之後安裝。 即使已將它發佈到半年通道 (如果您將系統設定至該通道進行測試), 或是甚至是由您自己的嘗試或設定手動推入時, 它將不會允許安裝, 除非我們結束時, 才能使用此選項。

Microsoft 團隊聊天室是「不在使用中」的「不在使用中」的功能, 不會因 Windows 更新而自動安裝 Windows 更新或重新開機裝置。 不過, 系統可能會下載更新, 並等待下一次重新開機來進行安裝。 除非有人手動重新開機, 否則系統會在自動重新開機時進行安裝。 Windows 更新在聊天室中應該是透明的, 而使用者介面不應該被 Windows 更新中斷。

如果您選擇 [加入網域], 請使用 SCCM 或 WSUS, 並特別注意策略或動作, 可能會導致裝置安裝更新, 或在營業期間強制重新開機。 如果您在部署期間重新開機您的系統, 或透過 UI 發出 Windows 更新通知, 您會想要查看您的設定。
