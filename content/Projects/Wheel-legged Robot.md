# Context
Ever watched Boston Dynamics' robots pulling off incredible stunts but thought "there's got to be a simpler way"? After diving into a research paper on wheel-legged robots and seeing the explosion of humanoid robots everywhere, I couldn't shake the feeling that we're overcomplicating robot mobility. So I set out to build something that combines the best of both worlds - the stability of wheels with the adaptability of legs!
Before jumping into CAD, I laid out some key goals:
- Stability First: The robot needed to handle rough terrain without the constant balancing act of humanoid designs
- Keep It Simple: Less components = fewer headaches (and fewer things to break!)
- Efficiency: Why waste energy constantly maintaining balance when you don't have to?
- Useful: it had to handle real-world scenarios
**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc5NvEk41izefZ2OJIBkiOL7G_62TFrGsR79Vx329jRibWK9V9pwTEjtuVAFc5qo51QrCHKWEsMnja0-IRRU-tDwdfreRPoLLQi6vKuTz-jdpiDY2qwIKAT4lWMOrn_jAWch-iSHQjLRyXBfd6vWwcT9J5B?key=zwGjVZ7EjAL1kdZw6LWOIA)**
# Leg Design
The core innovation of this design centers on the leg mechanism, which comprises four essential components working in harmony. The hip motor drives the system. It acts as the primary actuator. Position feedback enables precise motion control.
The thigh rod connects to the motor assembly. It bears the primary structural loads. This component is crucial for the parallelogram mechanism.
The drive rod maintains geometric alignment. It keeps platform orientation stable. Vertical motion becomes decoupled from body orientation.
The calf rod interfaces with the ground. It integrates the wheel assembly. Compliance mechanisms ensure smooth operation.
A single degree of freedom defines this system. It uses a parallelogram mechanism. This approach offers key advantages. The leg trajectory stays independent from body orientation. Control system complexity decreases significantly. Energy efficiency improves through simpler actuation.
**![|200](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf6-Aqcm9W6y80runQw6WgCobEclnM_y_jqTjMGv5_3BCBeGsGX6-_qk6spFWmrqpcEkVKUGnx6CZfQIxJqCKsqbCe0YXEvi8YXoceT7QEs7rKKcDCRxzw66oM45fS8_hA8lE8UyvSFMeDcOmueQ1inAbkq?key=zwGjVZ7EjAL1kdZw6LWOIA)******![|500](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdCBYlRy0VanTB6Tpi9tbbCywqv-0yEVjdDqUGmLGOALF4_SjuCmcPKpOf-tmnLWQief_plpx19X7rqFg-LzjsKQjVGa39p4qXoLPxugtxBsVwd8D0zRx7Hv2EdWEGe5Vso8FeBYB06gyD3bCFT8hQPETvE?key=zwGjVZ7EjAL1kdZw6LWOIA)
# Control System
I designed a dual-loop control architecture. The system separates body stabilization from leg motion. This separation maximizes stability performance.
Body stabilization uses LQR control. I selected four key state variables. Platform distance forms the position basis. Speed captures dynamic motion. Angle measures orientation deviation. Angular velocity completes the state feedback. Motor encoders deliver position data. An IMU provides orientation measurements.
I implemented state tracking as follows:

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcFHmsRG5mxsnoZj2doWdjKso-WeiVvamlGcoXpmfA3uJL1jqDxWe_n28U855-x8NqXHELmDetRCn7mfsEpke6cB9pVTFH4wxeQP3xpcbmu7hTNc42uYHCbkBKqSmG1r2ec7qylvmTPnFH5FVw31d_iKLzj?key=zwGjVZ7EjAL1kdZw6LWOIA)**

The system uses PID controllers for output generation. Each controller targets specific motion aspects. The outputs combine seamlessly. Real-time processing ensures smooth operation:

**![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf5ygAo5s7WUs3T1u1vgwZHeGBnukiyaKREiIoRJa9kRyGLpD3DpXzKxoiHrDUAfcpjPLYL_f__VLmBa8lw5KHutB0d6jMdDCQwRBKpGH1pbNXHybdqXIRgR3UvpoSNnVFl1SrIFv3gBELrIEQQIhoCSj8?key=zwGjVZ7EjAL1kdZw6LWOIA)**

I chose ADRC for leg motion control. This handles terrain variations effectively. It estimates unknown surface conditions. Compensation occurs automatically. The robot maintains stability across different surfaces.
# Electronic Integration
**![|300](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc6Ua7rF1yZps5-Mandqn9dDOO9Lx7pxaXfufus56VC3Stc3G7T9bcnfaMG6e7VPnfVzTXfL_4Sev-Gd35qAChC3QcyFvaav0Z265S9xxkqeTpFjStUK0fujqNXdBn6WNkLoU0BgU3fpBN3IyzlIFZx3P4C?key=zwGjVZ7EjAL1kdZw6LWOIA)****![|300](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeTUoJCI9OqzmCqmHK1F9zyNTnfWO003I9EFrcA5R4SHaRrqtyxC1ZaBxTidb9PTxTz5_pV0Wv68SVyFoYyvPrL2vMV2mRyg0F3_c3QIXoLg_fU7gsCCBO8wIwC0v-E9cc9467G6Io2cxH4zYJLV6go-T4R?key=zwGjVZ7EjAL1kdZw6LWOIA)**