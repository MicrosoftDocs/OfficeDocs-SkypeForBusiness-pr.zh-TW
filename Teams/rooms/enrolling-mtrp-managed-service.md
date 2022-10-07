---
title: 存取專業管理入口網站
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何存取Microsoft Teams 會議室專業管理入口網站。
f1keywords: ''
ms.openlocfilehash: 64d2613b586a5c87f42b6a376a6c3a0d9ad3a799
ms.sourcegitcommit: 43db97b84ca70b1e6accfa7214d4106e4177a642
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218077"
---
# <a name="accessing-the-pro-management-portal"></a>存取專業管理入口網站

若要存取Teams 會議室專業管理入口網站，您必須將一或多個使用者指派給受管理的服務系統管理員，然後使用該使用者完成註冊步驟。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>指派使用者給受管理的服務系統管理員角色

完成下列步驟，將使用者指派給受管理的服務系統管理員角色：

1. 使用與登入Microsoft 365 系統管理中心相同的系統管理員許可權，登入Teams 會議室[專業管理入口](https://portal.rooms.microsoft.com/)網站。
2. 流覽至 **[設定**  >  **設定**  >  **角色]**，然後選取 [**受管理的服務系統管理員]**。
3. 在 [ **受管理的服務系統管理員]** 底下，選取 [ **作業] 索引卷** 標，然後選取 [ **新增]**。
4. 請依照精靈為作業命名，然後選取應新增至作業的使用者。 作業將套用至所有會議室和會議室群組。
5. 在作業精靈的結尾，選取 **[新增作業]**。

指派受管理服務系統管理員角色的使用者負責日常管理和監控Teams 會議室。

將使用者指派給受管理的服務系統管理員角色之後，請繼續[前往註冊Teams 會議室裝置](enroll-a-device.md)以將Teams 會議室裝置新增至受管理的服務入口網站。

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
