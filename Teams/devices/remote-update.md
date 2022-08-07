---
title: 遠端更新 Microsoft Teams 裝置
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用 Teams 系統管理中心遠端更新 Microsoft Teams 手機、Teams 面板和共同作業列
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269458"
---
# <a name="update-microsoft-teams-devices-remotely"></a>遠端更新 Microsoft Teams 裝置

您可以使用 Microsoft Teams 系統管理中心，遠端更新 Teams 手機、Teams 面板和共同作業列等 Teams 裝置，並選擇裝置韌體自動更新行為。 您可以在裝置上使用 Teams 系統管理中心更新下列專案：

- Teams 應用程式和團隊系統管理員代理程式
- 公司入口網站應用程式
- OEM 代理程式應用程式
- 裝置韌體

裝置韌體更新可以自動套用或排定未來的日期和時間。 其他可用的裝置更新不會自動套用，但可以手動套用或排定未來的日期和時間。

> [!NOTE]
> 雖然可以排程裝置韌體更新，但如果排定的日期和時間落在設定的最多 30 或 90 天延遲之後，韌體更新會在到達最大延遲時套用。 排定的日期和時間會被忽略。 此外，從遠端更新 Microsoft Teams 裝置是美國政府雲端租使用者 (GCC-High) 尚未提供的功能。

若要管理裝置，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。如需系統管理員角色的詳細資訊，請參閱 [使用 Microsoft Teams 系統管理員角色管理 Teams](../using-admin-roles.md)。

## <a name="choose-automatic-device-firmware-update-behavior"></a>選擇自動裝置韌體更新行為

裝置韌體更新會自動套用。 如果您選擇此選項，您可以決定是否要在發行更新後立即套用更新 (，更新會在更新發行) 後的第一個週末套用，或在更新發行後的 30 或 90 天內套用。 根據預設，裝置韌體更新會在發行 30 天內套用。

> [!IMPORTANT]
> 最新的韌體更新版本不會套用至您的 Teams 裝置。 相反地，自動套用到您裝置上的更新會延遲一個版本。 例如，假設您的裝置已套用「10」版本，併發行「11」版本。 版本 「11」 尚未套用。 相反地，您的裝置只會在版本 「12」 發行後更新為版本 「11」。

> [!NOTE]
> 有些裝置還不支援自動韌體更新。 在不支援自動更新的裝置上套用自動韌體更新設定不會對這些裝置造成任何影響。 如需有關您的裝置是否支援自動韌體更新的問題，請連絡您的裝置製造商。

若要選擇裝置的自動更新行為，請執行下列動作：

1. 流覽以登入 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽 **Teams 裝置**  >  **IP 電話** 或 **共同作業列** 或 **Teams 面板**。
3. 選取一或多個裝置，然後選取 **[更新]**。
4. 在 **[韌體自動更新**] 底下，選取下列其中一項：
    - **一旦推出** 第二個最新的裝置韌體更新會在最新更新發行後的第一個週末套用。
    - **延遲 30 天** 第二個最新的裝置韌體更新會在最新更新發行後的 30 天內套用。
    - **延遲 90 天** 第二個最新的裝置韌體更新會在最新更新發行後 90 天套用。
5. 選取 **[更新]**。

如果因任何原因需要還原裝置韌體更新，您必須將裝置重設為原廠設定。 使用裝置製造商的指示重設您的裝置。  

## <a name="manually-update-remote-devices"></a>手動更新遠端裝置

當您使用系統管理中心更新一或多個裝置時，您可以決定是否要立即更新裝置，或是排定未來日期和時間的更新。

若要手動更新遠端裝置，請執行下列動作：

1. 流覽以登入 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽 **Teams 裝置**  >  **IP 電話** 或 **共同作業列** 或 **Teams 面板**。
3. 選取一或多個裝置，然後選取 **[更新]**。
4. 如果您想要針對未來的日期和時間排程更新，請在 **[手動更新**] 下方選取 [ **排** 程]。 更新會在時區中所選時區的日期和時間 **套用**。

您會看到的內容取決於您選取的是一個或多個裝置。 下圖顯示已選取多個裝置，而右側影像顯示已選取單一裝置。

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置檢視。":::

當您選取多個裝置時，您可以選擇要套用至每個選取裝置的更新類型。 選取您要套用的更新類型，然後選取 **[更新]**。

當您選取單一裝置時，會顯示裝置可用的更新。 如果裝置有多種可用的更新類型，請選取要套用的每個更新類型。 您可以檢視裝置上套用的 **目前版本** ，以及將會套用 **的新版本** 。 選取您要套用的更新 () ，然後選取 **[更新]**。

選取 **[更新**] 之後，如果您已排程更新，更新會在您選取的日期和時間套用到您的裝置。 如果您沒有選取未來的日期和時間，更新會在幾分鐘內套用到您的裝置。
