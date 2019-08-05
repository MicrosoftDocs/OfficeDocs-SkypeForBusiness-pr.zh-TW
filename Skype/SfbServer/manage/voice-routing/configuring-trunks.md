---
title: 在商務用 Skype Server 中設定 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在企業語音部署中, 您可以設定在中繼伺服器與一或多個對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線。
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187048"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 trunks

在企業語音部署中, 您可以設定在中繼伺服器與一或多個下列對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線:

- 網際網路電話服務提供者 (ITSP) 的 SIP 中繼連線
- PSTN 閘道
- 私人分支 exchange (PBX)

如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃 PSTN](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)連線。

> [!IMPORTANT]
> 開始中繼設定前, 請確認已建立拓撲, 且已設定並與其他中繼伺服器及其對等專案相關聯。 如需詳細資訊, 請參閱[在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。

> [!NOTE]
> 在主幹設定中, 您可以啟用商務用 Skype Server 媒體旁路功能, 這可讓媒體略過中繼伺服器。 Trunks 可以使用或不啟用媒體旁路進行設定, 但我們強烈建議您啟用它。 如需詳細資訊, 請參閱[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
