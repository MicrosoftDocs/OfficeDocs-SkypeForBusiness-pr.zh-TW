---
title: 新增 Edge 電腦內部 IP 2010
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。
ms.openlocfilehash: 45e35b42ee88736aa2422560e1a3df60d34ed31c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418496"
---
# <a name="add-edge-machine-internal-ip-2010"></a>新增 Edge 電腦內部 IP 2010

使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。

- 在 [ **內部 IPv4 位址**] 中，輸入要新增至集區之 Edge SERVER 的 IP 位址。

- 在 [ **內部 FQDN**] 中，輸入您要新增至集區之 Edge Server 的完整功能變數名稱 (FQDN) 。

您指定的 FQDN 必須與伺服器上設定的電腦名稱相同。 根據預設，未加入網域的電腦的電腦名稱是簡短名稱，不是 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定網域名稱系統 (DNS) 尾碼。 如需在電腦名稱中加上 DNS 尾碼的詳細資訊，請參閱＜[Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)＞。