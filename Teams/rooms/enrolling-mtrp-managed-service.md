---
title: 在受Teams 會議室服務中註冊Microsoft Teams 會議室 進階版裝置
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在受管理Microsoft Teams 會議室註冊Microsoft Teams 會議室 進階版帳戶。
f1keywords: ''
ms.openlocfilehash: 6ac3a9752fcb285c663e05939ae31b2e60a8a1e6
ms.sourcegitcommit: 3ebf9c5d27263b7e92163f1a61844a5367a4744f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "58449023"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>在受管理的服務中Microsoft Teams 會議室 進階版裝置

若要在受Microsoft Teams 會議室服務中註冊Teams 會議室 進階版，您需要將一個使用者指派給 Managed Service 系統管理員，然後使用該使用者完成註冊步驟。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>將使用者指派給 Managed Service 系統管理員角色

完成下列步驟，將使用者指派給 Managed Service 系統管理員角色：

1. 以與登入[](https://portal.rooms.microsoft.com/)Teams 會議室 進階版相同的系統管理員許可權登入 Microsoft 365 系統管理中心。
2. 流覽至  >  **設定設定**  >  **角色**，然後選取 **管理服務系統管理員**。
3. 在 **Managed Service 系統管理員的** 下， **選取作業選項卡** ， **然後選取新增**。
4. 請遵循精靈為作業命名，然後選取應該新增到該作業的使用者。 作業將適用于所有會議室和會議室群組。
5. 在作業精靈的結尾，選取 新增 **作業**。

指派受管理服務系統管理員角色的使用者負責管理及監控受管理Teams 會議室 進階版入口網站。

將使用者指派給受管理服務系統管理員角色之後，請繼續到註冊裝置區[](#enroll-a-teams-rooms-device)段，Teams 會議室裝置新到受管理服務入口網站。

## <a name="enroll-a-teams-rooms-device"></a>註冊Teams 會議室裝置

完成下列步驟，在受管理服務中註冊Teams 會議室 進階版裝置：

1. 使用指派[Teams 會議室 進階版](https://portal.rooms.microsoft.com/)服務系統管理員角色的使用者登入網站入口網站。
2. 選取 ？  入口網站右上角的圖示，以啟動説明功能表。 說明功能表包含包含 [詳細註冊](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 指示的安裝指南：

    1. 請閱 **覽安裝指南** 中的先決條件一節。 確認通訊所需的 URL 清單中所列的URL 已新加到防火牆的流量允許清單中。
    2. 請遵循啟用 **TPM** 設定區段的指示，在裝置上啟用信任的平臺模組 (TPM) 功能。
    3. 請遵循新增 Proxy **設定區段** 的指示，將裝置設定為使用 Proxy 閘道 ，如果您有。
    4. 請遵循 **程式區段** 的指示來安裝監控代理程式軟體，並在您的裝置上設定自我註冊金鑰。

3. 在裝置上配置監控代理程式及唯一 XML 鍵之後，請流覽至會議室>會議室名稱>**狀態**，然後 **選取註冊**。

    > [!NOTE]
    > 在Teams 會議室系統管理員使用入口網站註冊裝置之前，裝置會維持在登錄狀態。

## <a name="link-to-installation-guide"></a>安裝指南連結

說明 **功能表** 提供安裝指南 [的連結，進而](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 提供下列資訊：

- 需要允許列出才能將會議室遙測送往受管理服務之 URL 的指示。
- 將監控代理程式Microsoft Teams 會議室 進階版唯一 XML 金鑰作為註冊受管理服務之裝置之一部分的指示。
- 疑難排解指示。
