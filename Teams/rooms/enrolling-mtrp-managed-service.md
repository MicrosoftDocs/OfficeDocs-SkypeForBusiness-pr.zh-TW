---
title: 在受Teams 會議室服務中註冊Microsoft Teams 會議室進階版裝置
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在受管理Microsoft Teams 會議室註冊Microsoft Teams 會議室進階版帳戶。
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766966"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>在受管理的服務中Microsoft Teams 會議室進階版裝置

若要在受Microsoft Teams 會議室服務中註冊Teams 會議室 進階版，您需要將一個使用者指派給 Managed Service 系統管理員，然後使用該使用者完成註冊步驟。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>將使用者指派給 Managed Service 系統管理員角色

完成下列步驟，將使用者指派給 Managed Service 系統管理員角色：

1. 以與登入[](https://portal.rooms.microsoft.com/)Teams 會議室 進階版相同的系統管理員許可權登入 Microsoft 365 系統管理中心。
2. 流覽至  >  **設定設定**  >  **角色**，然後選取 **Managed Service 系統管理員**。
3. 在 **Managed Service 系統管理員的** 下， **選取作業選項卡** ， **然後選取新增**。
4. 請遵循精靈為作業命名，然後選取應該新增到該作業的使用者。 作業將適用于所有會議室和會議室群組。
5. 在作業精靈的結尾，選取 新增 **作業**。

指派受管理服務系統管理員角色的使用者負責管理及監控受管理Teams 會議室 進階版入口網站。

將使用者指派給受管理服務系統管理員角色之後，請繼續到註冊裝置區[](#enroll-a-teams-rooms-device)段，Teams 會議室裝置新到受管理服務入口網站。

## <a name="enroll-a-teams-rooms-device"></a>註冊Teams 會議室裝置

 若要在受管理服務中Teams 會議室 進階版裝置，請參閱[監控裝置軟體安裝](monitor-software-installation-guide.md)。

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
