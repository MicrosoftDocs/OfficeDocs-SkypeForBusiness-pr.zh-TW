---
title: 遠端更新 teams 裝置Microsoft
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
description: 使用 Teams 系統管理中心遠端更新 Android 裝置上的 Teams 手機、Teams 面板和Teams 會議室Microsoft。
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438261"
---
# <a name="update-microsoft-teams-devices-remotely"></a>遠端更新 teams 裝置Microsoft

您可以使用 Microsoft Teams 系統管理中心，遠端更新您的 Teams 裝置，例如 Teams 手機、Teams 面板和 Android 上的Teams 會議室。 您可以從 Teams 系統管理中心更新您裝置上的下列軟體元件：

- Teams 應用程式
- 裝置韌體

裝置韌體更新預設會自動進行。 不過，您可以手動更新韌體和其他軟體元件。 手動套用更新時，可以立即套用或排定未來的日期和時間。

只有經過Microsoft測試的韌體版本可透過 Teams 系統管理中心進行自動或手動更新。 經Microsoft測試的韌體版本會標示 **為Microsoft驗證**。 未通過Microsoft測試的韌體版本會標示為 **[未知的版本]**。 執行未知韌體版本的裝置無法自動更新;這些裝置只能手動更新。

若要管理裝置，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。如需系統管理員角色的詳細資訊，請參[閱使用 Microsoft Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)。

## <a name="assign-devices-to-an-automatic-update-phase"></a>指派裝置至自動更新階段

將裝置指派給自動更新階段是 Android 裝置上Teams 會議室的Teams 會議室專業版功能。 具有基本Teams 會議室授權的裝置將會指派給 [一般] 階段。 將會保留任何預先設定的階段，並且不允許進一步的變更。 如需詳細資訊，請[參閱Microsoft Teams 會議室授權](../rooms/rooms-licensing.md)。  

無法在 GCC High 中使用 Teams 系統管理中心自動更新 Teams 裝置。 不過，GCC High 中的組織可以使用 Teams 系統管理中心 [手動更新 Teams 裝置](#manually-update-remote-devices) 。

> [!IMPORTANT]
> 自動更新功能目前處於早期發行階段。 更新部署速度可能比您選取的階段慢。 在接下來幾個月內，自動部署更新的速度將會加快，直到它們到達您選取的階段為止。

> [!NOTE]
> 有些裝置尚不支援自動韌體更新。 在不支援自動更新的裝置上套用自動韌體更新設定不會對這些裝置有任何影響。 如需有關您的裝置是否支援自動韌體更新的問題，請連絡您的裝置製造商。
>
> 更新會在週末和一般上班時間外套用，以避免干擾。 階段內的裝置將會在數周內逐漸更新，而不是一次更新所有裝置。

若要選擇裝置的自動更新階段，請執行下列動作：

1. 流覽以登入Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽至 **Teams 裝置**，然後選取 [**手機**]、**[顯示器**]、[**面板****] 或 [在 Android 上Teams 會議室]**。  
3. 選取一或多個裝置，然後選取 **[更新]**。
4. 在 **[韌體自動更新**] 底下，選取下列其中一項：
    - **測試** 此選項最適合實驗室或測試裝置，您可以執行任何需要執行的驗證。 更新在最新韌體版本發行後立即開始部署。 先前稱為 **「儘快執行」**。
    - **一般** 這是預設選項，最適合您大部分的一般用途裝置。 更新在新韌體版本發行 30 天之後才開始部署。 先前稱為 **延期 30 天**。
    - **最後** 此選項最適合 VIP 使用的裝置，以及完成大型驗證之後的大型設定。 更新在新韌體版本發行 90 天之後才開始部署。 先前稱為 **延期 90 天**。
5. 選取 **[更新]**。

若要查看裝置處於哪個階段，請參閱 Teams 系統管理中心的 [ **韌體自動更新** ] 欄。 若要查看哪些裝置屬於特定階段的一部分，請使用 **[篩選** ] 選項搭配 **自動更新階段** 參數。

若要還原裝置韌體更新，您必須將裝置重設為原廠設定。 使用裝置製造商的指示重設您的裝置。  

## <a name="manually-update-remote-devices"></a>手動更新遠端裝置

如果您想要使用 Teams 系統管理中心手動更新裝置，您可以決定是否要立即更新裝置，或是排定未來日期和時間的更新。

若要手動更新遠端裝置，請執行下列動作：

1. 流覽以登入Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽 **Teams 裝置**，然後在 Android 上選取 **[手機**]、**[顯示器**]、[**面板****] 或 [Teams 會議室]**。
3. 選取一或多個裝置，然後選取 **[更新]**。
4. 如果您想要針對未來的日期和時間排程更新，請在 **[手動更新**] 下方選取 [ **排** 程]。 更新會在時區中所選時區的日期和時間 **套用**。

您會看到的內容取決於您選取的是一個或多個裝置。 下圖顯示已選取多個裝置，而右側影像顯示已選取單一裝置。

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置檢視。":::

當您選取多個裝置時，您可以選擇要套用至每個選取裝置的更新類型。 選取您要套用的更新類型，然後選取 **[更新]**。

當您選取單一裝置時，會顯示裝置可用的更新。 如果裝置有多種可用的更新類型，請選取要套用的每個更新類型。 您可以檢視裝置上套用的 **目前版本** ，以及將會套用 **的新版本** 。 選取您要套用的更新 () ，然後選取 **[更新]**。

選取 **[更新**] 之後，如果您已排程更新，更新會在您選取的日期和時間套用到您的裝置。 如果您沒有選取未來的日期和時間，更新會在幾分鐘內套用到您的裝置。
