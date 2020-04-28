---
title: 使用新式驗證登入 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 了解新式驗證如何運作、如何切換帳戶，以及如何疑難排解新式驗證。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43bbb3018b1c0cbe9f225a8a78acd4007b9232c2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903728"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式驗證登入 Microsoft Teams
==========================

Microsoft Teams 使用新式驗證讓登入體驗更加簡單可靠。 若要瞭解使用者如何登入 Teams，請閱讀[登入 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式驗證的運作方式

新式驗證是一種程序，可讓 Teams 知道使用者已經在別處輸入其認證 (例如他們的工作電子郵件和密碼)，因此不需要再次輸入就能啟動應用程式。 這項體驗會根據幾項因素而有所不同，例如使用者是在 Windows 或在 Mac 上工作。 它也會根據您的組織是啟用單一要素驗證還是多重要素驗證而有所不同 (多重要素驗證通常牽涉到透過手機，提供唯一的驗證碼、輸入 PIN 或呈現指紋來驗證認證)。 以下是每個新式驗證案例的摘要。

### <a name="windows-users"></a>Windows 使用者 

- 如果使用者已透過 Office 365 企業版帳戶登入其他 Office 應用程式，當他們啟動 Teams 時，就可以直接進入應用程式。 不需要輸入認證。

- 如果使用者未登入其 Office 365 企業版帳戶，當他們啟動 Teams 時，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，取決於您的組織決定要採取的程序。

- 如果使用者登入加入網域的電腦，當他們啟動 Teams 時，系統可能會要求他們執行一個進一步的驗證步驟，視您的組織是否選擇要求 MFA 或他們的電腦是否要求 MFA 才能登入而定。 如果使用者的電腦要求 MFA 才能登入，當他們開啟 Teams 時，應用程式會自動啟動。

- 如果使用者登入加入網域的電腦，但是您**不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。 


### <a name="mac-users"></a>Mac 使用者 

使用者啟動 Teams 時，他們的電腦無法從他們的 Office 365 企業版帳戶或其他任何 Office 應用程式中提取認證。 而是會顯示提示詢問他們進行 SFA 或 MFA (視您組織的設定而定)。 使用者輸入認證後，就不需要再次提供這些認證。 從這時起，只要他們在同一部電腦上工作，Teams 就會自動啟動。

## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式驗證後切換帳戶

如果使用者正在加入網域的電腦 (例如，如果其租用戶已啟用 Kerberos) 上工作，他們在完成新式驗證之後，就無法切換使用者帳戶。 如果使用者不是在加入網域的電腦上工作，他們就可以切換帳戶。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>完成新式驗證後登出 Teams
若要登出 Teams，使用者可以按一下應用程式頂端的個人檔案圖片，然後選取 **[登出]**，也可以在其工作列中的應用程式圖示上按一下滑鼠右鍵，然後選取 **[登出]**。登出 Teams 之後，必須再次輸入認證，才能啟動應用程式。

## <a name="urls-and-ip-address-ranges"></a>URL 和 IP 位址範圍
Teams 需要連線到網際網路。 若要瞭解客戶在 Office 365 方案、政府和其他雲端中使用 Teams 能夠連線的端點，請參閱 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 

> [!IMPORTANT]
> Teams 目前需要讓所有使用者存取 (TCP 通訊埠 443) 連線到 Google ssl.gstatic.com 服務 (https://ssl.gstatic.com)。即使您沒有使用 Gstatic 亦同。 Teams 很快會移除此要求 (2020 年初)，我們到時候也會更新本文。

## <a name="troubleshooting-modern-authentication"></a>疑難排解新式驗證

每個使用 Teams 的組織都能使用新式驗證，因此如果使用者無法完成程序，您的網域或組織的 Office 365 企業版帳戶可能有問題。 

如需詳細資訊，請參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

