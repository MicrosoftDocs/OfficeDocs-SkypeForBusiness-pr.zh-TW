---
title: 僅限團隊的模式考慮
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 準備升級至 [僅限 Microsoft 團隊] 模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1.keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89aded4747bc0a3f41fd78ce1bdced7b3363775b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708309"
---
# <a name="teams-only-mode-considerations"></a>僅限團隊的模式考慮

如果您是 Office 365 租使用者的系統管理員，您現在會在 Microsoft 團隊系統管理中心看到 [升級為團隊專用模式] 的選項。 使用此功能，您可以升級個別使用者或整個租使用者。  

升級至 [僅限團隊] 模式可透過單一用戶端體驗，為使用者提供 Microsoft 團隊的全部好處，即在 Office 365 中進行團隊合作的中心。 此外，[團隊專用] 模式中的使用者會在團隊中收到所有通話和聊天，不論寄件者是使用商務用 Skype 還是小組，以及互通性與同盟支援的好處。

雖然成千上萬的客戶已成功升級至 Microsoft 團隊，但在這種情況下，可能也會影響貴組織的升級時程表和使用者體驗。 特別是，升級選項並不一定表示貴組織已準備好進行這項變更。 為了獲得最佳使用者體驗，請確認 Teams 符合您的共同作業與通訊需求，並確認您的網路已準備好可支援 Teams，並在將使用者升級至 Teams 之前，先進行您的使用者整備計劃。 

> [!IMPORTANT]
> 如果您剛剛開始升級規劃，請務必複習我們的完整升級指導方針和規劃資源。 [從這裡開始](upgrade-start-here.md)。 

**共存考慮**：已使用商務用 skype Online 和/或商務用 skype 伺服器的組織，會以符合其需求的節奏，將小組引入他們的環境中。 組織可以視需要將團隊逐漸推出給所需的使用者組，而使用團隊的使用者可以與使用商務用 Skype 的使用者通訊，反之亦然。 若要管理此體驗，系統管理員會使用共存模式來定義最終使用者用戶端體驗、傳入聊天和通話的傳送行為，以及是否在團隊或商務用 Skype 中排程新會議。 如果使用者只升級至**團隊**，則使用者可以與其他組織中的使用者聯盟;不過，當兩個使用者都使用團隊時，就會提供最佳體驗。 已升級至團隊的使用者仍然可以加入商務用 Skype 會議。 

> [!NOTE]
> 已升級至團隊的使用者將無法與使用客戶用 Skype 的使用者進行通訊。

> [!IMPORTANT]
> 如需有關共存的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 

**整個租**使用者的考慮：我們正在努力在下列環境中啟用團隊;不過，如果您的商務用 Skype 租使用者是以下列其中一種環境為宿主，系統管理員就不應該升級組織中的任何使用者：

 - 政府社區雲端高
 - 政府社區雲端 DoD
 - 由世紀互聯運營的 Office 365
 - Office 365 德國
 - 商務用 Skype 租使用者託管于韓國 **，** 組織需要將團隊資料儲存在韓國中。 目前，以韓國所儲存的商務用 Skype 資料升級至團隊的組織，會將其小組資料儲存在亞太地區，而不是在韓國資料中心區域中。

**使用者專用的考慮**：有些使用者案例仍在演變，管理員可能會決定在升級組織中的其他使用者時，暫時推遲特定使用者的升級。 特別是，我們仍在針對主要裝置是使用 VDI 的使用者解決案例。 請監控[Office 365 藍圖](https://www.microsoft.com/en-us/microsoft-365/roadmap)網站以取得通知。

> [!NOTE]
> 在您移至 [僅限團隊] 模式前，您需要更換或更新不支援小組的裝置。 

> [!IMPORTANT]
> **請記住**： [移至] 團隊不只是技術遷移。 成功的升級會評估技術就緒性和最終使用者就緒性。 如需規劃升級至團隊的相關詳細資訊，請參閱商務用 Skype 的團隊[升級指導](upgrade-framework.md)方針。  
