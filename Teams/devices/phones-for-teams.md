---
title: Microsoft 團隊的電話
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文涵蓋針對 Microsoft 團隊認證的手機清單，以及手機認證中 Microsoft 團隊支援的功能。
ms.openlocfilehash: b017e02b2d3d2bdc6b01886929d034abb6650384
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583952"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft 團隊的電話

Microsoft 團隊可為需要傳統電話體驗的使用者支援一套手機。 本文提供團隊手機的完整概覽，並且可協助您規劃、交付及管理 Microsoft 手機系統解決方案中的 Microsoft 團隊手機。 

若要在手機上提供高品質且可靠的 Microsoft 團隊體驗，我們將與 Yealink、Crestron、聯想、Polycom 和 Audiocodes 共同合作，以開發及認證大量的手機和會議室音訊裝置。 若要取得團隊裝置最新及最新資訊，請移至 [[小組 Marketplace](https://office.com/teamsdevices)]。

## <a name="features-supported-by-teams-phones"></a>團隊手機支援的功能
小組認證的手機擁有多種功能，可協助您的使用者進行工作，並協助您管理他們的使用。 以下是團隊認證手機中可用功能的摘要：

- **驗證**手機使用新式驗證來簡化登入及提升安全性的功能。 使用者可以在手機上輸入他們的使用者名稱和密碼，或從其他裝置（例如 PC/smartphone）登入，以登入。
- **快速撥號和通話記錄**使用者可以快速存取他們的連絡人、通話記錄和語音信箱。 他們可以直接從手機管理連絡人及快速撥號專案。
- **會議和通話**使用者可以使用小組的單一觸控式連接來查看其排程，輕鬆加入會議。
- **通話群組**參與呼叫群組的電話代理程式可輕鬆管理其可用性，並接受或拒絕來自通話佇列的來電。
- **使用者委派**管理人員助理和系統管理員可以管理其主管電話-截獲來電;代表主管打電話給主管;接管總經理已保留的通話;然後監視主管是否在通話、保留等上。
- **熱 desking**使用者只要登入手機，就能取得他們的連絡人、會議及其他喜好設定。 完成後，他們就可以登出，並將手機留給下一位使用者。
- **影片**含視頻支援的手機可讓使用者加入通話和視訊會議，就像自己的電腦一樣。 使用者可以使用手機的相機快門和麥克風靜音開關（如果有的話）來保持隱私權。
- **更好地搭配**當您連線到執行64位團隊桌面用戶端的 Windows 電腦時，手機可以以整合的方式鎖定和解除鎖定。
- **協助工具**手機有數種協助工具功能（例如高對比文字），可讓任何人都能更輕鬆地使用。
- **動態及增強的 E911 支援**呼叫911的登入使用者會看到其在手機上的位置。 
    > [!IMPORTANT]
    > 如果電話未登入，或者如果沒有網際網路連線，則無法放置911通話。 如果發生這種情況，請在手機上顯示通知。

除了上述功能之外，您還可以根據指派給登入電話的使用者授權和電話原則類型，控制所提供的功能。 例如，使用個人帳戶登入手機的使用者可以存取完整的功能（通話、會議、語音信箱等）。 如果帳戶指派登入手機的常見區域電話授權，可能只會存取有限範圍的功能;您可能不會保留通話記錄及會議排程，例如保護使用者的隱私權。

## <a name="required-licenses"></a>所需授權

Microsoft 團隊授權可以在[microsoft 365 和 Office 365 訂閱](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)中購買。 若要深入瞭解在手機上使用 Microsoft 團隊所需的授權，請參閱可用的[電話系統授權](https://products.office.com/microsoft-teams/voice-calling)。

如需取得團隊的詳細資訊，請參閱[如何取得 Microsoft 團隊的存取權？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>透過 Intune 部署您的手機

### <a name="conditional-access"></a>條件式存取

條件式存取是 Azure Active Directory 功能，可協助您確保存取 Office 365 資源的裝置受到正確管理且安全。  如果您將條件式存取原則套用至 [團隊服務]，則 Android 裝置 (包括「團隊」電話) ，而 Access 小組需要註冊到 Intune，且其設定必須符合您的原則。  如果裝置未登錄至 Intune，或已登入，但其設定與您的原則不符，則條件式存取會防止使用者登入或使用裝置上的小組 app。

通常，在 Intune 中定義的規範原則會指派給使用者群組。  這表示如果您指派 Android 規範原則至 user@contoso.com，該原則會同等地套用到他們的 Android 智慧型手機，以及 user@contoso.com 登入的任何 Android 版的小組裝置。

如果您使用條件式存取（需要強制進行 Intune 註冊），在您的組織中，您需要設定幾個專案，才能允許成功進行 Intune 登記：

- **Intune 授權**登入 Microsoft 團隊手機的使用者必須具備 Intune 版授權。  只要 Microsoft 團隊手機登入擁有有效 Intune 授權的使用者帳戶，該電話就會自動登入 Microsoft Intune 中，做為登入處理常式的一部分。
- **設定 Intune**您必須為 Android 裝置系統管理員註冊設定正確設定的 Intune 租使用者。

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>將 Intune 設定為以 Android 版為基礎的裝置註冊團隊

在 Intune 中，以 Android 裝置管理員身分管理的團隊是由 android 裝置管理員 (DA) 管理。 在能將裝置登記到 Intune 之前，請先執行幾個基本步驟。  如果您目前已使用 Intune 管理裝置，您可能已經完成所有這些專案。  如果沒有，以下是要執行的動作：

1. 將 Intune MDM (行動裝置管理) 頒發機構設定。  如果您之前從未使用過 Intune，您必須先設定 MDM 頒發機構，才能註冊裝置。 如需詳細資訊，請參閱[設定行動裝置管理機構](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。  此為一次性步驟，必須在建立新的 Intune 租使用者完成。
2. 啟用 Android 裝置管理員註冊。 Android 版的團隊裝置是使用 Intune 作為裝置系統管理員裝置進行管理。  新建立的租使用者預設會關閉 [裝置管理員註冊]。  如需詳細資訊，請參閱[Android 裝置系統管理員註冊](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. 指派授權給使用者。 必須為團隊裝置使用者註冊到 Intune 的使用者指派有效的 Intune 授權。 如需詳細資訊，請參閱[指派授權給使用者，讓他們可以在 Intune 中註冊裝置](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。
4. 指派裝置管理員合規性原則。  建立 Android 裝置管理員合規性原則，並將它指派給 Azure Active Directory 群組，該群組包含要登入小組裝置的使用者。 如需詳細資訊，請參閱[使用合規性策略來設定您使用 Intune 管理的裝置規則](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="manage-your-phones"></a>管理您的手機

租使用者管理員可以透過 [小組系統管理中心]，管理並將其所有團隊的裝置保持在最新狀態。 如需詳細資訊，請參閱[在 Microsoft 團隊中管理您的裝置](https://docs.microsoft.com/microsoftteams/devices/device-management)。 

## <a name="see-also"></a>另請參閱

[團隊 Marketplace](https://office.com/teamsdevices)

[Microsoft 團隊的 IP 手機認證](teams-ip-phones.md)
