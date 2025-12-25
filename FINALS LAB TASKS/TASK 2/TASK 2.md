PROBLEM

<img width="543" height="524" alt="image" src="https://github.com/user-attachments/assets/bdcd4f88-e983-4079-ad54-95ad50afb1f0" />


SOURCE CODE

      import tkinter as tk
      from tkinter import ttk
      from tkinter import messagebox
      
      
      class GradeCalculator:
          def __init__(self, root):
              self.root = root
              root.title("Grade Calculator")
              root.configure(bg="light gray")
      
              input_frame = tk.Frame(root, bg="light gray")
              input_frame.grid(row=0, column=0, padx=10, pady=5, sticky="nw")
      
              tk.Label(input_frame, text="Prelim Grade:", bg="light gray").grid(
                  row=0, column=0, padx=5, pady=2, sticky="e"
              )
              self.prelim_entry = tk.Entry(input_frame)
              self.prelim_entry.grid(row=0, column=1, padx=5, pady=2)
      
              tk.Label(input_frame, text="Midterm Grade:", bg="light gray").grid(
                  row=1, column=0, padx=5, pady=2, sticky="e"
              )
              self.midterm_entry = tk.Entry(input_frame)
              self.midterm_entry.grid(row=1, column=1, padx=5, pady=2)
      
              tk.Label(input_frame, text="Pre Finals Grade:", bg="light gray").grid(
                  row=2, column=0, padx=5, pady=2, sticky="e"
              )
              self.pre_finals_entry = tk.Entry(input_frame)
              self.pre_finals_entry.grid(row=2, column=1, padx=5, pady=2)
      
              tk.Label(input_frame, text="Final Grade:", bg="light gray").grid(
                  row=3, column=0, padx=5, pady=2, sticky="e"
              )
              self.final_grade_entry = tk.Entry(input_frame)
              self.final_grade_entry.grid(row=3, column=1, padx=5, pady=2)
      
              option_frame = tk.Frame(root, bg="light gray")
              option_frame.grid(row=1, column=0, padx=10, pady=5, sticky="nw")
      
              tk.Label(option_frame, text="Choose an Option:", bg="light gray").grid(
                  row=0, column=0, padx=5, pady=2, sticky="e"
              )
      
              self.grade_type = ttk.Combobox(
                  option_frame, values=["Letter Grade", "Numeric Grade"], state="readonly"
              )
              self.grade_type.grid(row=0, column=1, padx=5, pady=2)
              self.grade_type.set("Letter Grade")
      
              summary_frame = tk.Frame(root, bg="light gray")
              summary_frame.grid(row=2, column=0, padx=10, pady=5, sticky="nw")
      
              self.output_text = tk.Text(summary_frame, height=10, width=35, state="disabled")
              self.output_text.grid(row=0, column=0, padx=5, pady=2)
      
              buttons_frame = tk.Frame(root, bg="light gray")
              buttons_frame.grid(row=3, column=0, padx=10, pady=5)
      
              tk.Button(buttons_frame, text="Compute", command=self.compute_gpa).grid(
                  row=0, column=0, padx=5, pady=2
              )
              tk.Button(buttons_frame, text="Reset", command=self.reset_fields).grid(
                  row=0, column=1, padx=5, pady=2
              )
              tk.Button(buttons_frame, text="About", command=self.show_about).grid(
                  row=0, column=2, padx=5, pady=2
              )
              tk.Button(buttons_frame, text="Close", command=root.destroy).grid(
                  row=0, column=3, padx=5, pady=2
              )
      
          def compute_gpa(self):
              try:
                  prelim = float(self.prelim_entry.get())
                  midterm = float(self.midterm_entry.get())
                  pre_finals = float(self.pre_finals_entry.get())
                  final_grade = float(self.final_grade_entry.get())
      
                  gpa = (prelim + midterm + (0.5 * pre_finals) + (0.5 * final_grade)) / 3
      
                  if self.grade_type.get() == "Letter Grade":
                      grade_equivalent = self.get_letter_grade(gpa)
                  else:
                      grade_equivalent = self.get_numeric_grade(gpa)
      
                  remarks = self.get_remarks(gpa)
      
                  output = (
                      f"Prelim Grade: {prelim}\n"
                      f"Midterm Grade: {midterm}\n"
                      f"Pre Finals: {pre_finals}\n"
                      f"Finals: {final_grade}\n"
                      f"GPA: {gpa:.2f}\n"
                      f"{self.grade_type.get()}: {grade_equivalent}\n"
                      f"Remarks: {remarks}"
                  )
      
                  self.output_text.config(state="normal")
                  self.output_text.delete("1.0", tk.END)
                  self.output_text.insert(tk.END, output)
                  self.output_text.config(state="disabled")
      
              except ValueError:
                  messagebox.showerror("Error", "Please enter valid numeric grades.")
      
          def get_letter_grade(self, gpa):
              if 96 <= gpa <= 100:
                  return "A"
              elif 93 <= gpa <= 95:
                  return "A-"
              elif 88 <= gpa <= 92:
                  return "B+"
              elif 83 <= gpa <= 87:
                  return "B"
              elif 78 <= gpa <= 82:
                  return "C+"
              elif 76 <= gpa <= 77:
                  return "C"
              elif gpa == 75:
                  return "D"
              elif 65 <= gpa <= 74:
                  return "F"
              else:
                  return "Invalid"
      
          def get_numeric_grade(self, gpa):
              if 97 <= gpa <= 100:
                  return "1.0"
              elif 94 <= gpa <= 96:
                  return "1.25"
              elif 90 <= gpa <= 93:
                  return "1.50"
              elif 87 <= gpa <= 89:
                  return "1.75"
              elif 84 <= gpa <= 86:
                  return "2.0"
              elif 81 <= gpa <= 83:
                  return "2.25"
              elif 78 <= gpa <= 80:
                  return "2.50"
              elif 76 <= gpa <= 77:
                  return "2.75"
              elif gpa == 75:
                  return "3.0"
              elif 65 <= gpa <= 74:
                  return "5.0"
              else:
                  return "Invalid"
      
          def get_remarks(self, gpa):
              return "PASSED" if gpa >= 75 else "FAILED"
      
          def reset_fields(self):
              self.prelim_entry.delete(0, tk.END)
              self.midterm_entry.delete(0, tk.END)
              self.pre_finals_entry.delete(0, tk.END)
              self.final_grade_entry.delete(0, tk.END)
              self.output_text.config(state="normal")
              self.output_text.delete("1.0", tk.END)
              self.output_text.config(state="disabled")
              self.grade_type.set("Letter Grade")
      
          def show_about(self):
              messagebox.showinfo(
                  "About",
                  "Hello! We are Salonga, Francis and Centeno, John Kurt."
              )
      
      
      if __name__ == "__main__":
          root = tk.Tk()
          GradeCalculator(root)
          root.mainloop()

OUTPUT

<img width="714" height="353" alt="image" src="https://github.com/user-attachments/assets/09a58ad8-26f2-499b-9ce3-e4396f565e93" />

