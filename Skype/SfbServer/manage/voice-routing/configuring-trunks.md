---
title: 在商務用 Skype Server 中設定主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在企業語音部署中，您可以設定轉送伺服器與一或多位對等之間的主幹，為組織中的 Enterprise Voice 用戶端和裝置提供公用交換電話網路 (PSTN) 連線能力。
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800113"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中設定主幹

在企業語音部署中，您可以設定轉送伺服器與一或多個下列對等間的主幹，為組織中的 Enterprise Voice 用戶端和裝置提供公用交換電話網路 (PSTN) 連線能力：

- 網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線
- PSTN 閘道
- 專用交換機 (Private branch exchange，PBX)

如需詳細資訊，請參閱 [Plan FOR PSTN connectivity In 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> 在您開始進行主幹設定之前，請確認已建立拓撲，而且中繼伺服器及其對等已設定好，並彼此產生關聯。 如需詳細資訊，請參閱 [在商務用 Skype Server 的拓撲產生器中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。

> [!NOTE]
> 作為主幹設定的一部分，您可以啟用商務用 Skype Server 媒體旁路功能，讓媒體略過轉送伺服器。 不論是否啟用媒體旁路功能，都可以設定主幹，但強烈建議您啟用該功能。 如需詳細資訊，請參閱 [Plan for media 旁路 In 商務用 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
