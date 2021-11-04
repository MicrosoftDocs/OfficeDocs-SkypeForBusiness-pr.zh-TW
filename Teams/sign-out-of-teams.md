---
title: 登出 Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: 瞭解如何登出 Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fb1048f0db6166dbbcd7f43c317db2603b57dd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750082"
---
# <a name="sign-out-of-microsoft-teams"></a>登出 Microsoft Teams

我們建議使用者保持 Microsoft Teams 應用程式的登入狀態，以繼續接收聊天、來電及其他活動。 我們瞭解，有時使用者可能會因為數個原因而想要登出 Teams 應用程式:

- 因為他們已使用 Teams 一天
- 他們想要使用不同的帳戶
- 因為他們位於與另一個人分享的裝置上

由於這些及其他原因，Teams 可讓您登出應用程式並結束您的工作階段。

## <a name="account-sharing-between-apps"></a>應用程式之間的帳戶共用

新式作業系統允許在裝置上的不同應用程式之間共用帳戶。 這個單一登入 （SSO） 設計可讓使用者在裝置上使用多個應用程式，而不需要他們在每一個應用程式都進行登入。 Teams 不會控制此行為，但會利用此設計為使用者體驗提供的便利性。

SSO 對登出有重要影響。當使用者登出 Teams 時，與其帳戶相關聯的資料會從 Teams 應用程式中移除，但裝置上的其他應用程式可以繼續存取其帳戶。 這也表示如果使用者選擇使用相同的帳戶重新登入 Teams，系統可能不會提示使用者重新輸入認證。

## <a name="sign-out-of-teams-on-desktop"></a>登出電腦版 Teams

若要登出 Teams 電腦用戶端或從瀏覽器登出，請選取應用程式頂端的個人資料圖片，然後選取 **登出**。

對於傳統型應用程式，您也可以以滑鼠右鍵按一下工作列中的應用程式圖示，然後選取 **登出**。

如果您新增了多個帳戶，您必須登出每個個別帳戶。 一旦在 Teams 中登出帳戶後，您可能需要在下次啟動應用程式時再次輸入您的認證，才能存取您的帳戶。

## <a name="sign-out-of-teams-on-mobile-devices"></a>在行動裝置上登出 Teams

在行動裝置上, 您可以移至功能表，選取 **[更多]** 功能表，然後選取 **[登出]**，以登出 Teams。一旦登出，則需在下一次啟動該應用程式時，重新輸入認證。

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>適用於前線工作者的全域登入和登出

Teams Android 應用程式現在支援全域登入和登出，為前線員工提供輕鬆便利的登入和登出體驗。 員工可以從共用裝置集區中挑選一部裝置，並執行單一登入，以在其輪班期間「讓它成為自己的裝置」。 在班次結束時，他們應該能夠執行登出，以便在裝置上全域登出。 這會自裝置移除其個人與公司資訊，他們便能將裝置歸還裝置集區。 若要取得這項功能，裝置必須處於共用模式。 若要瞭解如何設定共用裝置，請參閱 [如何在 Android 上使用共用裝置模式](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。

## <a name="manual-cleanup"></a>手動清除

雖然很少見，但 Teams 在完全登出後可能無法進行清除。根據使用者報告，常見原因包括檔案被系統執行的服務鎖定，但可能還有其他原因取決於個人的裝置設定或原則，以及裝置上所套用的使用者權限。

此問題的一個常見徵兆是, Teams 會嘗試自動選取現有的帳戶以將使用者登入。 在這種情況下，使用者可能會想要手動清除 Teams 的本地快取記憶體。 若要深入瞭解, 請至 [從 Teams 中登入或移除帳戶](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)。

## <a name="related-topics"></a>相關主題

[從 Teams 中登入或移除帳戶](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)