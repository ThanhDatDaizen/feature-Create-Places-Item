"use client";

import React, { useState } from "react";
import { Card, Button, Switch, Modal } from "antd";

const PlacesComponent = () => {
  const [isModalVisible, setIsModalVisible] = useState(false);
  const [isActive, setIsActive] = useState(true);

  const showModal = () => {
    setIsModalVisible(true);
  };

  const handleOk = () => {
    setIsModalVisible(false);
  };

  const handleCancel = () => {
    setIsModalVisible(false);
  };

  const toggleActive = () => {
    setIsActive(!isActive);
  };

  return (
    <div className="flex p-5 max-w-sm mx-auto">
      <Card
        style={{ borderRadius: "8px", boxShadow: "0 2px 8px rgba(0,0,0,0.1)" }}
      >
        <div className="flex">
          <div className="w-1/3">
            <img
              alt="cover"
              src="https://via.placeholder.com/150"
              className="rounded-l-lg w-full h-full object-cover"
            />
          </div>
          <div className="w-2/3 p-4">
            <Card.Meta
              title="Quán Phở Kê - CN2"
              description={
                <>
                  <p>
                    <strong>Address:</strong> B11B/13C Võ Văn Vân, Ấp 2, Vĩnh Lộc B, Bình Chánh, Tp HCM
                  </p>
                  <p>
                    <strong>Description:</strong> Phở Kê là quán ăn tuyệt vời cho những ai đam mê phở!
                  </p>
                  <p>
                    <strong>Đang hoạt động</strong>

                  </p>
                  <Button type="primary" onClick={showModal}>
            View
          </Button>
                </>
              }
            />
          </div>
        </div>




      </Card>

      <Modal
        title="Quán Phở Kê - CN1"
        open={isModalVisible}
        onOk={handleOk}
        onCancel={handleCancel}
      >
        <p>
          <strong>Chi nhánh 1</strong> <br />
          Địa chỉ: B11B/13C Võ Văn Vân, Ấp 2, Vĩnh Lộc B, Bình Chánh, Tp HCM <br />
          Description: Phở Kê là quán ăn tuyệt vời cho những ai đam mê phở!
        </p>
      </Modal>
    </div>
  );
};

export default PlacesComponent;
